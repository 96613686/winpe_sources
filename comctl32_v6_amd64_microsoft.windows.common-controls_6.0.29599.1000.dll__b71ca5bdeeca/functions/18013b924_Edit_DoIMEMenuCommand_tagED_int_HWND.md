# Edit_DoIMEMenuCommand(tagED *,int,HWND__ *)

- ea: `0x18013b924`
- end: `0x18013bb73`
- name: `?Edit_DoIMEMenuCommand@@YAHPEAUtagED@@HPEAUHWND__@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(struct tagED *, int, HWND)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18013be80`

## callees

- `0x180058f5c`
- `0x180059000`
- `0x18005d8bc`
- `0x1800e5330`
- `0x180114520`
- `0x18013b924`
- `0x1801d0c48`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013b9a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013bad0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013b9a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013bad0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013b9b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013b9b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013bade`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013bade`
- `USER32!SendMessageW` at `0x18013ba93`
- `USER32!SendMessageA` at `0x18013ba9a`
- `IMM32!ImmGetContext` at `0x18013b967`
- `IMM32!ImmGetContext` at `0x18013b967`
- `IMM32!ImmReleaseContext` at `0x18013bb43`
- `IMM32!ImmReleaseContext` at `0x18013bb43`
- `IMM32!ImmSetCompositionStringW` at `0x18013ba5e`
- `IMM32!ImmSetCompositionStringW` at `0x18013baca`
- `IMM32!ImmSetCompositionStringW` at `0x18013ba5e`
- `IMM32!ImmSetCompositionStringW` at `0x18013baca`
- `IMM32!ImmEnumInputContext` at `0x18013bb1c`
- `IMM32!ImmEnumInputContext` at `0x18013bb1c`
- `IMM32!ImmSetOpenStatus` at `0x18013bb37`
- `IMM32!ImmSetOpenStatus` at `0x18013bb37`
- `IMM32!ImmGetConversionStatus` at `0x18013baf9`
- `IMM32!ImmGetConversionStatus` at `0x18013baf9`
- `IMM32!ImmGetOpenStatus` at `0x18013bb27`
- `IMM32!ImmGetOpenStatus` at `0x18013bb27`

## pseudocode

```c
__int64 __fastcall Edit_DoIMEMenuCommand(struct tagED *a1, int a2, HWND a3)
{
  HIMC Context; // rax
  HIMC v7; // rsi
  int v8; // ebx
  int v9; // ebx
  __int64 v11; // rbp
  unsigned int v12; // r15d
  DWORD v13; // r13d
  HANDLE ProcessHeap; // rax
  _DWORD *v15; // r14
  char *v16; // rax
  int v17; // r9d
  unsigned int v18; // edx
  LRESULT (__stdcall *v19)(HWND, UINT, WPARAM, LPARAM); // rax
  HANDLE v20; // rax
  BOOL OpenStatus; // eax
  DWORD fdwConversion; // [rsp+30h] [rbp-48h] BYREF

  if ( a2 != 10001 && (unsigned int)(a2 - 10002) > 1 )
    return 0;
  Context = ImmGetContext(a3);
  v7 = Context;
  if ( Context )
  {
    v8 = a2 - 10001;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        if ( v9 != 1 )
          return 0;
        v11 = (unsigned int)(*((_DWORD *)a1 + 7) - *((_DWORD *)a1 + 6));
        v12 = v11 * *((unsigned __int16 *)a1 + 63);
        v13 = v12 + 40;
        ProcessHeap = GetProcessHeap();
        v15 = HeapAlloc(ProcessHeap, 0, v12 + 40);
        if ( v15 )
        {
          fdwConversion = *((_DWORD *)a1 + 6);
          v16 = Edit_Lock(a1);
          if ( v16 )
          {
            *v15 = v13;
            v15[1] = 0;
            v15[6] = v11;
            v15[4] = v11;
            v15[2] = v11;
            v15[3] = 32;
            v15[7] = 0;
            v15[5] = 0;
            memcpy_0(v15 + 8, &v16[*((_DWORD *)a1 + 6) * *((unsigned __int16 *)a1 + 63)], v12);
            *((_WORD *)v15 + v11 + 16) = 0;
            Edit_Unlock(a1);
            Edit_InOutReconversionMode(a1, 1);
            Edit_ImmSetCompositionWindow(a1, 0, 0);
            ImmSetCompositionStringW(v7, 0x20000u, v15, v13, 0, 0);
            v17 = v15[4];
            if ( v17 != (_DWORD)v11 || fdwConversion != *((_DWORD *)a1 + 6) )
            {
              v19 = SendMessageW;
              if ( (*((_DWORD *)a1 + 29) & 0x400000) != 0 )
                v19 = SendMessageA;
              v18 = v15[5] / (unsigned int)*((unsigned __int16 *)a1 + 63) + fdwConversion;
              ((void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))v19)(*((_QWORD *)a1 + 8), 177, v18, v18 + v17);
            }
            ImmSetCompositionStringW(v7, 0x10000u, v15, v13, 0, 0);
          }
          v20 = GetProcessHeap();
          HeapFree(v20, 0, v15);
        }
      }
      else
      {
        fdwConversion = 0;
        if ( ImmGetConversionStatus(Context, &fdwConversion, 0) )
          ImmEnumInputContext(0, Edit_EnumInputContextCB, (~fdwConversion >> 7) & 1);
      }
    }
    else
    {
      OpenStatus = ImmGetOpenStatus(Context);
      ImmSetOpenStatus(v7, !OpenStatus);
    }
    ImmReleaseContext(a3, v7);
  }
  return 1;
}

```

## disassembly

```asm
0x18013b924  mov     [rsp+arg_8], rbx
0x18013b929  push    rbp
0x18013b92a  push    rsi
0x18013b92b  push    rdi
0x18013b92c  push    r12
0x18013b92e  push    r13
0x18013b930  push    r14
0x18013b932  push    r15
0x18013b934  sub     rsp, 40h
0x18013b938  mov     rax, cs:__security_cookie
0x18013b93f  xor     rax, rsp
0x18013b942  mov     [rsp+78h+var_40], rax
0x18013b947  mov     rdi, rcx
0x18013b94a  mov     ebp, 2711h
0x18013b94f  mov     ecx, edx
0x18013b951  mov     r12, r8
0x18013b954  mov     ebx, edx
0x18013b956  sub     ecx, ebp
0x18013b958  jz      short loc_18013B964
0x18013b95a  sub     ecx, 1
0x18013b95d  jz      short loc_18013B964
0x18013b95f  cmp     ecx, 1
0x18013b962  jnz     short loc_18013B98F
0x18013b964  mov     rcx, r12; HWND
0x18013b967  call    cs:__imp_ImmGetContext
0x18013b96d  mov     rsi, rax
0x18013b970  test    rax, rax
0x18013b973  jz      loc_18013BB49
0x18013b979  sub     ebx, ebp
0x18013b97b  jz      loc_18013BB24
0x18013b981  sub     ebx, 1
0x18013b984  jz      loc_18013BAE6
0x18013b98a  cmp     ebx, 1
0x18013b98d  jz      short loc_18013B996
0x18013b98f  xor     eax, eax
0x18013b991  jmp     loc_18013BB4E
0x18013b996  mov     ebp, [rdi+1Ch]
0x18013b999  sub     ebp, [rdi+18h]
0x18013b99c  movzx   r15d, word ptr [rdi+7Eh]
0x18013b9a1  imul    r15d, ebp
0x18013b9a5  lea     r13d, [r15+28h]
0x18013b9a9  call    cs:__imp_GetProcessHeap
0x18013b9af  mov     r8d, r13d; dwBytes
0x18013b9b2  xor     edx, edx; dwFlags
0x18013b9b4  mov     rcx, rax; hHeap
0x18013b9b7  call    cs:__imp_HeapAlloc
0x18013b9bd  xor     ebx, ebx
0x18013b9bf  mov     r14, rax
0x18013b9c2  test    rax, rax
0x18013b9c5  jz      loc_18013BB3D
0x18013b9cb  mov     eax, [rdi+18h]
0x18013b9ce  mov     rcx, rdi; struct tagED *
0x18013b9d1  mov     [rsp+78h+fdwConversion], eax
0x18013b9d5  call    ?Edit_Lock@@YAPEADPEAUtagED@@@Z; Edit_Lock(tagED *)
0x18013b9da  test    rax, rax
0x18013b9dd  jz      loc_18013BAD0
0x18013b9e3  mov     [r14], r13d
0x18013b9e6  lea     rcx, [r14+20h]; void *
0x18013b9ea  mov     [r14+4], ebx
0x18013b9ee  mov     [r14+18h], ebp
0x18013b9f2  mov     [r14+10h], ebp
0x18013b9f6  mov     [r14+8], ebp
0x18013b9fa  mov     dword ptr [r14+0Ch], 20h ; ' '
0x18013ba02  mov     [r14+1Ch], ebx
0x18013ba06  mov     [r14+14h], ebx
0x18013ba0a  movzx   edx, word ptr [rdi+7Eh]
0x18013ba0e  imul    edx, [rdi+18h]
0x18013ba12  mov     r8d, r15d; Size
0x18013ba15  add     rdx, rax; Src
0x18013ba18  call    memcpy_0
0x18013ba1d  xor     r15d, r15d
0x18013ba20  mov     rcx, rdi; struct tagED *
0x18013ba23  mov     [r14+rbp*2+20h], r15w
0x18013ba29  call    ?Edit_Unlock@@YAXPEAUtagED@@@Z; Edit_Unlock(tagED *)
0x18013ba2e  lea     edx, [rbx+1]; int
0x18013ba31  mov     rcx, rdi; struct tagED *
0x18013ba34  call    ?Edit_InOutReconversionMode@@YAXPEAUtagED@@H@Z; Edit_InOutReconversionMode(tagED *,int)
0x18013ba39  xor     r8d, r8d; int
0x18013ba3c  xor     edx, edx; int
0x18013ba3e  mov     rcx, rdi; struct tagED *
0x18013ba41  call    ?Edit_ImmSetCompositionWindow@@YAXPEAUtagED@@JJ@Z; Edit_ImmSetCompositionWindow(tagED *,long,long)
0x18013ba46  mov     r9d, r13d; dwCompLen
0x18013ba49  mov     [rsp+78h+dwReadLen], r15d; dwReadLen
0x18013ba4e  mov     r8, r14; lpComp
0x18013ba51  mov     [rsp+78h+lpRead], r15; lpRead
0x18013ba56  mov     edx, 20000h; dwIndex
0x18013ba5b  mov     rcx, rsi; HIMC
0x18013ba5e  call    cs:__imp_ImmSetCompositionStringW
0x18013ba64  mov     r9d, [r14+10h]
0x18013ba68  mov     r8d, [rsp+78h+fdwConversion]
0x18013ba6d  cmp     r9d, ebp
0x18013ba70  jnz     short loc_18013BA78
0x18013ba72  cmp     r8d, [rdi+18h]
0x18013ba76  jz      short loc_18013BAB2
0x18013ba78  movzx   ecx, word ptr [rdi+7Eh]
0x18013ba7c  xor     edx, edx
0x18013ba7e  mov     eax, [r14+14h]
0x18013ba82  div     ecx
0x18013ba84  test    dword ptr [rdi+74h], 400000h
0x18013ba8b  mov     rcx, [rdi+40h]
0x18013ba8f  lea     edx, [rax+r8]
0x18013ba93  mov     rax, cs:__imp_SendMessageW
0x18013ba9a  cmovnz  rax, cs:__imp_SendMessageA
0x18013baa2  add     r9d, edx
0x18013baa5  mov     r8d, edx
0x18013baa8  mov     edx, 0B1h
0x18013baad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013bab2  mov     [rsp+78h+dwReadLen], r15d; dwReadLen
0x18013bab7  mov     r9d, r13d; dwCompLen
0x18013baba  mov     r8, r14; lpComp
0x18013babd  mov     [rsp+78h+lpRead], r15; lpRead
0x18013bac2  mov     edx, 10000h; dwIndex
0x18013bac7  mov     rcx, rsi; HIMC
0x18013baca  call    cs:__imp_ImmSetCompositionStringW
0x18013bad0  call    cs:__imp_GetProcessHeap
0x18013bad6  mov     r8, r14; lpMem
0x18013bad9  xor     edx, edx; dwFlags
0x18013badb  mov     rcx, rax; hHeap
0x18013bade  call    cs:__imp_HeapFree
0x18013bae4  jmp     short loc_18013BB3D
0x18013bae6  xor     r8d, r8d; lpfdwSentence
0x18013bae9  mov     [rsp+78h+fdwConversion], 0
0x18013baf1  lea     rdx, [rsp+78h+fdwConversion]; lpfdwConversion
0x18013baf6  mov     rcx, rsi; HIMC
0x18013baf9  call    cs:__imp_ImmGetConversionStatus
0x18013baff  test    eax, eax
0x18013bb01  jz      short loc_18013BB3D
0x18013bb03  mov     r8d, [rsp+78h+fdwConversion]
0x18013bb08  lea     rdx, ?Edit_EnumInputContextCB@@YAHPEAUHIMC__@@_J@Z; lpfn
0x18013bb0f  not     r8d
0x18013bb12  xor     ecx, ecx; idThread
0x18013bb14  shr     r8, 7
0x18013bb18  and     r8d, 1; lParam
0x18013bb1c  call    cs:__imp_ImmEnumInputContext
0x18013bb22  jmp     short loc_18013BB3D
0x18013bb24  mov     rcx, rsi; HIMC
0x18013bb27  call    cs:__imp_ImmGetOpenStatus
0x18013bb2d  xor     edx, edx
0x18013bb2f  mov     rcx, rsi; HIMC
0x18013bb32  test    eax, eax
0x18013bb34  setz    dl; BOOL
0x18013bb37  call    cs:__imp_ImmSetOpenStatus
0x18013bb3d  mov     rdx, rsi; HIMC
0x18013bb40  mov     rcx, r12; HWND
0x18013bb43  call    cs:__imp_ImmReleaseContext
0x18013bb49  mov     eax, 1
0x18013bb4e  mov     rcx, [rsp+78h+var_40]
0x18013bb53  xor     rcx, rsp; StackCookie
0x18013bb56  call    __security_check_cookie
0x18013bb5b  mov     rbx, [rsp+78h+arg_8]
0x18013bb63  add     rsp, 40h
0x18013bb67  pop     r15
0x18013bb69  pop     r14
0x18013bb6b  pop     r13
0x18013bb6d  pop     r12
0x18013bb6f  pop     rdi
0x18013bb70  pop     rsi
0x18013bb71  pop     rbp
0x18013bb72  retn
```
