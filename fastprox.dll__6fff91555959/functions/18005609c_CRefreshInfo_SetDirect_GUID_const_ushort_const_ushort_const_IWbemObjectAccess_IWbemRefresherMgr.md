# CRefreshInfo::SetDirect(_GUID const &,ushort const *,ushort const *,IWbemObjectAccess *,_IWbemRefresherMgr *)

- ea: `0x18005609c`
- end: `0x1800562b5`
- name: `?SetDirect@CRefreshInfo@@QEAAJAEBU_GUID@@PEBG1PEAUIWbemObjectAccess@@PEAU_IWbemRefresherMgr@@@Z`
- size: `537`
- prototype: `int(CRefreshInfo *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, struct IWbemObjectAccess *, struct _IWbemRefresherMgr *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800548a0`
- `0x1800558a4`

## callees

- `0x180037120`
- `0x180055e10`
- `0x18005609c`
- `0x180086450`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800560bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800560bd`
- `wbemcomn!GetMemLogObject` at `0x1800560cb`
- `wbemcomn!GetMemLogObject` at `0x180056142`
- `wbemcomn!GetMemLogObject` at `0x1800561bb`
- `wbemcomn!GetMemLogObject` at `0x1800560cb`
- `wbemcomn!GetMemLogObject` at `0x180056142`
- `wbemcomn!GetMemLogObject` at `0x1800561bb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800560db`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180056152`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800561cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800560db`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180056152`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800561cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRefreshInfo::SetDirect(
        CRefreshInfo *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IWbemObjectAccess *a5,
        struct _IWbemRefresherMgr *a6)
{
  unsigned __int16 **v10; // rax
  unsigned __int16 **v11; // rsi
  CMemoryLog *v12; // rax
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rbx
  CMemoryLog *v16; // rax
  unsigned __int16 *v17; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 **v20; // [rsp+20h] [rbp-38h] BYREF
  char v21; // [rsp+28h] [rbp-30h]
  unsigned __int16 *v22; // [rsp+30h] [rbp-28h] BYREF
  char v23; // [rsp+38h] [rbp-20h]
  unsigned __int16 *v24; // [rsp+40h] [rbp-18h] BYREF
  char v25; // [rsp+48h] [rbp-10h]

  v10 = (unsigned __int16 **)CoTaskMemAlloc(0x10u);
  v11 = v10;
  if ( v10 )
  {
    v20 = v10;
    v21 = 0;
    v14 = WbemStringCopy(a3);
    v15 = v14;
    if ( v14 )
    {
      v24 = v14;
      v25 = 0;
      v17 = WbemStringCopy(a4);
      if ( v17 )
      {
        v22 = v17;
        v21 = 1;
        v25 = 1;
        v23 = 1;
        *(_DWORD *)this = 1;
        *((_DWORD *)this + 12) = 0;
        *(struct _GUID *)((char *)this + 8) = *a2;
        *((_QWORD *)this + 3) = v11;
        *v11 = v15;
        *(_QWORD *)(*((_QWORD *)this + 3) + 8LL) = v17;
        *((_QWORD *)this + 4) = a5;
        *((_QWORD *)this + 5) = a6;
        if ( a5 )
          ((void (__fastcall *)(struct IWbemObjectAccess *))a5->lpVtbl->AddRef)(a5);
        if ( a6 )
          (*(void (__fastcall **)(struct _IWbemRefresherMgr *))(*(_QWORD *)a6 + 8LL))(a6);
        OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>((__int64)&v22);
        v13 = 0;
      }
      else
      {
        MemLogObject = GetMemLogObject();
        v13 = -2147217402;
        CMemoryLog::Write(MemLogObject, -2147217402);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_c58dba40f457377ce3dbee0d04a91c30_Traceguids,
            2147749894LL);
        }
      }
      OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>((__int64)&v24);
    }
    else
    {
      v16 = GetMemLogObject();
      v13 = -2147217402;
      CMemoryLog::Write(v16, -2147217402);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_c58dba40f457377ce3dbee0d04a91c30_Traceguids, 2147749894LL);
      }
    }
    OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>((__int64)&v20);
  }
  else
  {
    v12 = GetMemLogObject();
    v13 = -2147217402;
    CMemoryLog::Write(v12, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_c58dba40f457377ce3dbee0d04a91c30_Traceguids, 2147749894LL);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18005609c  push    rbp
0x18005609e  push    rbx
0x18005609f  push    rsi
0x1800560a0  push    rdi
0x1800560a1  push    r14
0x1800560a3  push    r15
0x1800560a5  mov     rbp, rsp
0x1800560a8  sub     rsp, 58h
0x1800560ac  mov     r14, r9
0x1800560af  mov     rbx, r8
0x1800560b2  mov     r15, rdx
0x1800560b5  mov     rdi, rcx
0x1800560b8  mov     ecx, 10h; cb
0x1800560bd  call    cs:__imp_CoTaskMemAlloc
0x1800560c3  mov     rsi, rax
0x1800560c6  test    rax, rax
0x1800560c9  jnz     short loc_18005612A
0x1800560cb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800560d1  mov     ebx, 80041006h
0x1800560d6  mov     edx, ebx
0x1800560d8  mov     rcx, rax
0x1800560db  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800560e1  lea     rax, WPP_GLOBAL_Control
0x1800560e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800560ef  cmp     rcx, rax
0x1800560f2  jz      loc_1800562A6
0x1800560f8  test    byte ptr [rcx+1Ch], 1
0x1800560fc  jz      loc_1800562A6
0x180056102  cmp     byte ptr [rcx+19h], 2
0x180056106  jb      loc_1800562A6
0x18005610c  lea     edx, [rsi+0Dh]
0x18005610f  mov     r9d, 80041006h
0x180056115  lea     r8, WPP_c58dba40f457377ce3dbee0d04a91c30_Traceguids
0x18005611c  mov     rcx, [rcx+10h]
0x180056120  call    WPP_SF_d
0x180056125  jmp     loc_1800562A6
0x18005612a  mov     [rbp+var_38], rsi
0x18005612e  mov     [rbp+var_30], 0
0x180056132  mov     rcx, rbx; unsigned __int16 *
0x180056135  call    ?WbemStringCopy@@YAPEAGPEBG@Z; WbemStringCopy(ushort const *)
0x18005613a  mov     rbx, rax
0x18005613d  test    rax, rax
0x180056140  jnz     short loc_1800561A3
0x180056142  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180056148  mov     ebx, 80041006h
0x18005614d  mov     edx, ebx
0x18005614f  mov     rcx, rax
0x180056152  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180056158  lea     rax, WPP_GLOBAL_Control
0x18005615f  mov     rcx, cs:WPP_GLOBAL_Control
0x180056166  cmp     rcx, rax
0x180056169  jz      loc_18005629D
0x18005616f  test    byte ptr [rcx+1Ch], 1
0x180056173  jz      loc_18005629D
0x180056179  cmp     byte ptr [rcx+19h], 2
0x18005617d  jb      loc_18005629D
0x180056183  mov     edx, 0Eh
0x180056188  mov     r9d, 80041006h
0x18005618e  lea     r8, WPP_c58dba40f457377ce3dbee0d04a91c30_Traceguids
0x180056195  mov     rcx, [rcx+10h]
0x180056199  call    WPP_SF_d
0x18005619e  jmp     loc_18005629D
0x1800561a3  mov     [rbp+var_18], rbx
0x1800561a7  mov     [rbp+var_10], 0
0x1800561ab  mov     rcx, r14; unsigned __int16 *
0x1800561ae  call    ?WbemStringCopy@@YAPEAGPEBG@Z; WbemStringCopy(ushort const *)
0x1800561b3  mov     rcx, rax
0x1800561b6  test    rax, rax
0x1800561b9  jnz     short loc_180056219
0x1800561bb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800561c1  mov     ebx, 80041006h
0x1800561c6  mov     edx, ebx
0x1800561c8  mov     rcx, rax
0x1800561cb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800561d1  lea     rax, WPP_GLOBAL_Control
0x1800561d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800561df  cmp     rcx, rax
0x1800561e2  jz      loc_180056293
0x1800561e8  test    byte ptr [rcx+1Ch], 1
0x1800561ec  jz      loc_180056293
0x1800561f2  cmp     byte ptr [rcx+19h], 2
0x1800561f6  jb      loc_180056293
0x1800561fc  mov     edx, 0Fh
0x180056201  mov     r9d, 80041006h
0x180056207  lea     r8, WPP_c58dba40f457377ce3dbee0d04a91c30_Traceguids
0x18005620e  mov     rcx, [rcx+10h]
0x180056212  call    WPP_SF_d
0x180056217  jmp     short loc_180056293
0x180056219  mov     [rbp+var_28], rcx
0x18005621d  mov     [rbp+var_20], 0
0x180056221  mov     [rbp+var_30], 1
0x180056225  mov     [rbp+var_10], 1
0x180056229  mov     [rbp+var_20], 1
0x18005622d  mov     dword ptr [rdi], 1
0x180056233  mov     dword ptr [rdi+30h], 0
0x18005623a  movups  xmm0, xmmword ptr [r15]
0x18005623e  movdqu  xmmword ptr [rdi+8], xmm0
0x180056243  mov     [rdi+18h], rsi
0x180056247  mov     [rsi], rbx
0x18005624a  mov     rax, [rdi+18h]
0x18005624e  mov     [rax+8], rcx
0x180056252  mov     rcx, [rbp+arg_20]
0x180056256  mov     [rdi+20h], rcx
0x18005625a  mov     rbx, [rbp+arg_28]
0x18005625e  mov     [rdi+28h], rbx
0x180056262  test    rcx, rcx
0x180056265  jz      short loc_180056273
0x180056267  mov     rax, [rcx]
0x18005626a  mov     rax, [rax+8]
0x18005626e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056273  test    rbx, rbx
0x180056276  jz      short loc_180056288
0x180056278  mov     rax, [rbx]
0x18005627b  mov     rcx, rbx
0x18005627e  mov     rax, [rax+8]
0x180056282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056287  nop
0x180056288  lea     rcx, [rbp+var_28]
0x18005628c  call    ??1?$OnDeleteIf@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@QEAA@XZ; OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>(void)
0x180056291  xor     ebx, ebx
0x180056293  lea     rcx, [rbp+var_18]
0x180056297  call    ??1?$OnDeleteIf@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@QEAA@XZ; OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>(void)
0x18005629c  nop
0x18005629d  lea     rcx, [rbp+var_38]
0x1800562a1  call    ??1?$OnDeleteIf@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@QEAA@XZ; OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>(void)
0x1800562a6  mov     eax, ebx
0x1800562a8  add     rsp, 58h
0x1800562ac  pop     r15
0x1800562ae  pop     r14
0x1800562b0  pop     rdi
0x1800562b1  pop     rsi
0x1800562b2  pop     rbx
0x1800562b3  pop     rbp
0x1800562b4  retn
```
