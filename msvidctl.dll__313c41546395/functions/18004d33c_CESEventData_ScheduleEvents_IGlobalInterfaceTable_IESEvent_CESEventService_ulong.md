# CESEventData::ScheduleEvents(IGlobalInterfaceTable *,IESEvent *,CESEventService *,ulong)

- ea: `0x18004d33c`
- end: `0x18004d555`
- name: `?ScheduleEvents@CESEventData@@QEAAJPEAUIGlobalInterfaceTable@@PEAUIESEvent@@PEAVCESEventService@@K@Z`
- size: `537`
- prototype: `__int64 __usercall@<rax>(LPARAM lParam@<rcx>, struct IGlobalInterfaceTable *@<rdx>, struct IESEvent *@<r8>, struct CESEventService *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004cae0`

## callees

- `0x180006b38`
- `0x18004d1a8`
- `0x18004d33c`
- `0x1800f8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18004d44e`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18004d44e`
- `KERNEL32!GetLastError` at `0x18004d4e8`
- `KERNEL32!GetLastError` at `0x18004d4e8`
- `USER32!PostThreadMessageW` at `0x18004d4de`
- `USER32!PostThreadMessageW` at `0x18004d4de`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CESEventData::ScheduleEvents(
        LPARAM lParam,
        struct IGlobalInterfaceTable *a2,
        struct IESEvent *a3,
        struct CESEventService *a4,
        DWORD idThread)
{
  signed int v9; // ebx
  unsigned __int64 v10; // rax
  int v11; // r15d
  __int64 v12; // r14
  int v13; // esi
  __int64 v14; // rax
  _DWORD *v15; // rcx
  signed int LastError; // eax
  __int64 v18; // [rsp+30h] [rbp-20h] BYREF
  __int64 v19; // [rsp+38h] [rbp-18h] BYREF
  __int128 v20; // [rsp+40h] [rbp-10h] BYREF
  int v21; // [rsp+90h] [rbp+40h] BYREF
  int v22; // [rsp+A0h] [rbp+50h] BYREF

  v19 = 0;
  v18 = 0;
  v9 = ((__int64 (__fastcall *)(struct IESEvent *, LPARAM))a3->lpVtbl->GetEventType)(a3, lParam + 16);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(char *, LPARAM, __int64 *))(*((_QWORD *)a4 + 2) + 32LL))(
           (char *)a4 + 16,
           lParam + 16,
           &v19);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 56LL))(v19, &v18);
      while ( v9 >= 0 )
      {
        v20 = 0;
        v22 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, int *))(*(_QWORD *)v18 + 24LL))(
               v18,
               1,
               &v20,
               &v22);
        if ( v9 < 0 || !v22 )
          break;
        v10 = *(int *)(lParam + 8);
        v11 = v10 + 1;
        if ( (int)v10 + 1 > 0 )
        {
          if ( (_DWORD)v10 != *(_DWORD *)(lParam + 12) )
          {
            v12 = *(int *)(lParam + 8);
LABEL_15:
            *(_DWORD *)(lParam + 8) = v11;
            v15 = (_DWORD *)(*(_QWORD *)lParam + 4 * v12);
            if ( v15 )
              *v15 = DWORD2(v20);
            goto LABEL_18;
          }
          if ( (int)v10 <= 0x3FFFFFFF )
          {
            v12 = *(int *)(lParam + 8);
            if ( v10 <= 0x1FFFFFFFFFFFFFFFLL )
            {
              v13 = 1;
              if ( *(_DWORD *)(lParam + 12) )
                v13 = 2 * v10;
              v14 = _o_realloc(*(_QWORD *)lParam, 4LL * v13);
              if ( v14 )
              {
                *(_DWORD *)(lParam + 12) = v13;
                *(_QWORD *)lParam = v14;
                goto LABEL_15;
              }
            }
          }
        }
        v9 = -2147024882;
LABEL_18:
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v20 + 16LL))(v20);
      }
    }
  }
  v21 = 0;
  if ( v9 < 0 )
    goto LABEL_27;
  v9 = ((__int64 (__fastcall *)(struct IGlobalInterfaceTable *, struct IESEvent *, GUID *, int *))a2->lpVtbl->RegisterInterfaceInGlobal)(
         a2,
         a3,
         &IID_IESEvent,
         &v21);
  if ( v9 < 0 )
    goto LABEL_25;
  *(_DWORD *)(lParam + 32) = v21;
  if ( !PostThreadMessageW(idThread, 0x8000u, 0x135Du, lParam) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v9 < 0 )
  {
LABEL_25:
    if ( v21 )
    {
      ((void (__fastcall *)(struct IGlobalInterfaceTable *))a2->lpVtbl->RevokeInterfaceFromGlobal)(a2);
      *(_DWORD *)(lParam + 32) = 0;
    }
LABEL_27:
    ATL::CSimpleArray<unsigned long>::RemoveAll(lParam);
  }
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v18);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v19);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004d33c  mov     [rsp-38h+arg_8], rbx
0x18004d341  push    rbp
0x18004d342  push    rsi
0x18004d343  push    rdi
0x18004d344  push    r12
0x18004d346  push    r13
0x18004d348  push    r14
0x18004d34a  push    r15
0x18004d34c  mov     rbp, rsp
0x18004d34f  sub     rsp, 50h
0x18004d353  mov     r14, r9
0x18004d356  mov     r13, r8
0x18004d359  mov     r12, rdx
0x18004d35c  mov     rdi, rcx
0x18004d35f  mov     [rbp+var_18], 0
0x18004d367  mov     [rbp+var_20], 0
0x18004d36f  mov     rax, [r8]
0x18004d372  lea     rdx, [rcx+10h]
0x18004d376  mov     rcx, r8
0x18004d379  mov     rax, [rax+20h]
0x18004d37d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d382  mov     ebx, eax
0x18004d384  test    eax, eax
0x18004d386  js      loc_18004D498
0x18004d38c  lea     rcx, [r14+10h]
0x18004d390  mov     rax, [rcx]
0x18004d393  lea     r8, [rbp+var_18]
0x18004d397  lea     rdx, [rdi+10h]
0x18004d39b  mov     rax, [rax+20h]
0x18004d39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3a4  mov     ebx, eax
0x18004d3a6  test    eax, eax
0x18004d3a8  js      loc_18004D498
0x18004d3ae  mov     rcx, [rbp+var_18]
0x18004d3b2  mov     rax, [rcx]
0x18004d3b5  lea     rdx, [rbp+var_20]
0x18004d3b9  mov     rax, [rax+38h]
0x18004d3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3c2  mov     ebx, eax
0x18004d3c4  test    eax, eax
0x18004d3c6  js      loc_18004D498
0x18004d3cc  xorps   xmm0, xmm0
0x18004d3cf  movups  [rbp+var_10], xmm0
0x18004d3d3  mov     [rbp+arg_10], 0
0x18004d3da  mov     rcx, [rbp+var_20]
0x18004d3de  mov     rax, [rcx]
0x18004d3e1  lea     r9, [rbp+arg_10]
0x18004d3e5  lea     r8, [rbp+var_10]
0x18004d3e9  mov     edx, 1
0x18004d3ee  mov     rax, [rax+18h]
0x18004d3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3f7  mov     ebx, eax
0x18004d3f9  test    eax, eax
0x18004d3fb  js      loc_18004D498
0x18004d401  cmp     [rbp+arg_10], 0
0x18004d405  jz      loc_18004D498
0x18004d40b  movsxd  rax, dword ptr [rdi+8]
0x18004d40f  lea     r15d, [rax+1]
0x18004d413  test    r15d, r15d
0x18004d416  jle     short loc_18004D47B
0x18004d418  cmp     eax, [rdi+0Ch]
0x18004d41b  jnz     short loc_18004D461
0x18004d41d  cmp     eax, 3FFFFFFFh
0x18004d422  jg      short loc_18004D47B
0x18004d424  mov     r14, rax
0x18004d427  mov     rcx, 1FFFFFFFFFFFFFFFh
0x18004d431  cmp     rax, rcx
0x18004d434  ja      short loc_18004D47B
0x18004d436  cmp     dword ptr [rdi+0Ch], 0
0x18004d43a  mov     esi, 1
0x18004d43f  jz      short loc_18004D444
0x18004d441  lea     esi, [rax+rax]
0x18004d444  movsxd  rdx, esi
0x18004d447  shl     rdx, 2
0x18004d44b  mov     rcx, [rdi]
0x18004d44e  call    cs:__imp__o_realloc
0x18004d454  test    rax, rax
0x18004d457  jz      short loc_18004D47B
0x18004d459  mov     [rdi+0Ch], esi
0x18004d45c  mov     [rdi], rax
0x18004d45f  jmp     short loc_18004D464
0x18004d461  mov     r14, rax
0x18004d464  mov     [rdi+8], r15d
0x18004d468  mov     rax, [rdi]
0x18004d46b  lea     rcx, [rax+r14*4]
0x18004d46f  test    rcx, rcx
0x18004d472  jz      short loc_18004D480
0x18004d474  mov     eax, dword ptr [rbp+var_10+8]
0x18004d477  mov     [rcx], eax
0x18004d479  jmp     short loc_18004D480
0x18004d47b  mov     ebx, 8007000Eh
0x18004d480  mov     rcx, qword ptr [rbp+var_10]
0x18004d484  mov     rax, [rcx]
0x18004d487  mov     rax, [rax+10h]
0x18004d48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d490  test    ebx, ebx
0x18004d492  jns     loc_18004D3CC
0x18004d498  mov     [rbp+arg_0], 0
0x18004d49f  test    ebx, ebx
0x18004d4a1  js      short loc_18004D51F
0x18004d4a3  mov     rax, [r12]
0x18004d4a7  lea     r9, [rbp+arg_0]
0x18004d4ab  lea     r8, IID_IESEvent
0x18004d4b2  mov     rdx, r13
0x18004d4b5  mov     rcx, r12
0x18004d4b8  mov     rax, [rax+18h]
0x18004d4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4c1  mov     ebx, eax
0x18004d4c3  test    eax, eax
0x18004d4c5  js      short loc_18004D501
0x18004d4c7  mov     eax, [rbp+arg_0]
0x18004d4ca  mov     [rdi+20h], eax
0x18004d4cd  mov     r9, rdi; lParam
0x18004d4d0  mov     edx, 8000h; Msg
0x18004d4d5  mov     r8d, 135Dh; wParam
0x18004d4db  mov     ecx, [rbp+idThread]; idThread
0x18004d4de  call    cs:__imp_PostThreadMessageW
0x18004d4e4  test    eax, eax
0x18004d4e6  jnz     short loc_18004D4FD
0x18004d4e8  call    cs:__imp_GetLastError
0x18004d4ee  mov     ebx, eax
0x18004d4f0  test    eax, eax
0x18004d4f2  jle     short loc_18004D4FD
0x18004d4f4  movzx   ebx, ax
0x18004d4f7  or      ebx, 80070000h
0x18004d4fd  test    ebx, ebx
0x18004d4ff  jns     short loc_18004D528
0x18004d501  mov     edx, [rbp+arg_0]
0x18004d504  test    edx, edx
0x18004d506  jz      short loc_18004D51F
0x18004d508  mov     rax, [r12]
0x18004d50c  mov     rcx, r12
0x18004d50f  mov     rax, [rax+20h]
0x18004d513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d518  mov     dword ptr [rdi+20h], 0
0x18004d51f  mov     rcx, rdi
0x18004d522  call    ?RemoveAll@?$CSimpleArray@K@ATL@@QEAAXXZ; ATL::CSimpleArray<ulong>::RemoveAll(void)
0x18004d527  nop
0x18004d528  lea     rcx, [rbp+var_20]
0x18004d52c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18004d531  nop
0x18004d532  lea     rcx, [rbp+var_18]
0x18004d536  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18004d53b  mov     eax, ebx
0x18004d53d  mov     rbx, [rsp+50h+arg_8]
0x18004d545  add     rsp, 50h
0x18004d549  pop     r15
0x18004d54b  pop     r14
0x18004d54d  pop     r13
0x18004d54f  pop     r12
0x18004d551  pop     rdi
0x18004d552  pop     rsi
0x18004d553  pop     rbp
0x18004d554  retn
```
