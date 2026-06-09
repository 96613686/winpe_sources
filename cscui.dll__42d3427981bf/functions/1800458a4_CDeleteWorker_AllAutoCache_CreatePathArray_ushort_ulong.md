# CDeleteWorker_AllAutoCache::_CreatePathArray(ushort * * *,ulong *)

- ea: `0x1800458a4`
- end: `0x180045acd`
- name: `?_CreatePathArray@CDeleteWorker_AllAutoCache@@AEAAJPEAPEAPEAGPEAK@Z`
- size: `553`
- prototype: `__int64 __fastcall(CDeleteWorker_AllAutoCache *__hidden this, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180045390`

## callees

- `0x180003c20`
- `0x180013d9c`
- `0x1800321b8`
- `0x180033154`
- `0x1800458a4`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045a4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045a4c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800458f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800458f7`

## pseudocode

```c
__int64 __fastcall CDeleteWorker_AllAutoCache::_CreatePathArray(
        CDeleteWorker_AllAutoCache *this,
        unsigned __int16 ***a2,
        unsigned int *a3)
{
  HRESULT StringCopy; // ebx
  unsigned int v6; // edi
  int v7; // eax
  unsigned __int16 **v8; // r14
  __int64 v9; // rsi
  void *v10; // rdx
  __int64 j; // rsi
  LPVOID ppv; // [rsp+30h] [rbp-10h] BYREF
  CDeleteWorker_AllAutoCache *v14; // [rsp+80h] [rbp+40h] BYREF
  __int64 i; // [rsp+88h] [rbp+48h] BYREF
  __int64 v16; // [rsp+90h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+58h] BYREF

  v14 = this;
  *a2 = 0;
  *a3 = 0;
  ppv = 0;
  StringCopy = CoCreateInstance(&CLSID_OfflineFilesCache, 0, 1u, &GUID_3836f049_9413_45dd_bf46_b5aaa82dc310, &ppv);
  if ( StringCopy >= 0 )
  {
    v16 = 0;
    StringCopy = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, 0, &v16);
    if ( StringCopy >= 0 )
    {
      v6 = 0;
      LODWORD(v14) = 0;
      for ( i = 0; ; i = 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, CDeleteWorker_AllAutoCache **))(*(_QWORD *)v16 + 24LL))(
               v16,
               1,
               &i,
               &v14);
        StringCopy = v7;
        if ( v7 )
          break;
        ++v6;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)i + 16LL))(i);
      }
      if ( v7 >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 40LL))(v16);
        pv = 0;
        StringCopy = CscUtil_HeapAllocArray<_ITEMID_CHILD *>(v6, &pv);
        if ( StringCopy >= 0 )
        {
          v8 = (unsigned __int16 **)pv;
          v9 = 0;
          do
          {
            if ( (unsigned int)v9 >= v6 )
              goto LABEL_22;
            StringCopy = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, CDeleteWorker_AllAutoCache **))(*(_QWORD *)v16 + 24LL))(
                           v16,
                           1,
                           &i,
                           &v14);
            if ( StringCopy )
              break;
            pv = 0;
            StringCopy = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)i + 32LL))(i, &pv);
            if ( StringCopy >= 0 )
            {
              StringCopy = CscUtil_CreateStringCopy((const unsigned __int16 *)pv, &v8[v9]);
              if ( StringCopy >= 0 )
              {
                v9 = (unsigned int)(v9 + 1);
                if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
                {
                  WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_110f8852164937b701b00ed210f9da85_Traceguids, pv);
                }
              }
              CoTaskMemFree(pv);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)i + 16LL))(i);
            i = 0;
          }
          while ( StringCopy >= 0 );
          if ( StringCopy >= 0 )
          {
LABEL_22:
            *a2 = v8;
            *a3 = v6;
            goto LABEL_23;
          }
          for ( j = 0; (unsigned int)j < v6; j = (unsigned int)(j + 1) )
            CscUtil_HeapFree(v8[j], v10);
          CscUtil_HeapFree(v8, v10);
        }
      }
LABEL_23:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)StringCopy;
}

```

## disassembly

```asm
0x1800458a4  mov     [rsp-38h+arg_0], rcx
0x1800458a9  push    rbp
0x1800458aa  push    rbx
0x1800458ab  push    rsi
0x1800458ac  push    rdi
0x1800458ad  push    r12
0x1800458af  push    r14
0x1800458b1  push    r15
0x1800458b3  mov     rbp, rsp
0x1800458b6  sub     rsp, 40h
0x1800458ba  mov     r15, r8
0x1800458bd  mov     qword ptr [rdx], 0
0x1800458c4  mov     r12, rdx
0x1800458c7  mov     dword ptr [r8], 0
0x1800458ce  lea     rax, [rbp+var_10]
0x1800458d2  mov     [rbp+var_10], 0
0x1800458da  mov     esi, 1
0x1800458df  mov     [rsp+40h+ppv], rax; ppv
0x1800458e4  mov     r8d, esi; dwClsContext
0x1800458e7  lea     r9, _GUID_3836f049_9413_45dd_bf46_b5aaa82dc310; riid
0x1800458ee  xor     edx, edx; pUnkOuter
0x1800458f0  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x1800458f7  call    cs:__imp_CoCreateInstance
0x1800458fd  mov     ebx, eax
0x1800458ff  test    eax, eax
0x180045901  js      loc_180045ABC
0x180045907  mov     rcx, [rbp+var_10]
0x18004590b  lea     r8, [rbp+arg_10]
0x18004590f  mov     [rbp+arg_10], 0
0x180045917  xor     edx, edx
0x180045919  mov     rax, [rcx]
0x18004591c  mov     rax, [rax+18h]
0x180045920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045925  mov     ebx, eax
0x180045927  test    eax, eax
0x180045929  js      loc_180045AAC
0x18004592f  xor     edi, edi
0x180045931  mov     dword ptr [rbp+arg_0], edi
0x180045934  mov     [rbp+arg_8], rdi
0x180045938  mov     rcx, [rbp+arg_10]
0x18004593c  lea     r9, [rbp+arg_0]
0x180045940  lea     r8, [rbp+arg_8]
0x180045944  mov     edx, esi
0x180045946  mov     rax, [rcx]
0x180045949  mov     rax, [rax+18h]
0x18004594d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045952  mov     ebx, eax
0x180045954  test    eax, eax
0x180045956  jnz     short loc_180045974
0x180045958  mov     rcx, [rbp+arg_8]
0x18004595c  add     edi, esi
0x18004595e  mov     rax, [rcx]
0x180045961  mov     rax, [rax+10h]
0x180045965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004596a  mov     [rbp+arg_8], 0
0x180045972  jmp     short loc_180045938
0x180045974  js      loc_180045A9C
0x18004597a  mov     rcx, [rbp+arg_10]
0x18004597e  mov     rax, [rcx]
0x180045981  mov     rax, [rax+28h]
0x180045985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004598a  mov     ecx, edi
0x18004598c  lea     rdx, [rbp+pv]
0x180045990  mov     [rbp+pv], 0
0x180045998  call    ??$CscUtil_HeapAllocArray@PEAU_ITEMID_CHILD@@@@YAJ_KPEAPEAPEAU_ITEMID_CHILD@@@Z; CscUtil_HeapAllocArray<_ITEMID_CHILD *>(unsigned __int64,_ITEMID_CHILD * * *)
0x18004599d  mov     ebx, eax
0x18004599f  test    eax, eax
0x1800459a1  js      loc_180045A9C
0x1800459a7  mov     r14, [rbp+pv]
0x1800459ab  xor     esi, esi
0x1800459ad  cmp     esi, edi
0x1800459af  jnb     loc_180045A95
0x1800459b5  mov     rcx, [rbp+arg_10]
0x1800459b9  lea     r9, [rbp+arg_0]
0x1800459bd  lea     r8, [rbp+arg_8]
0x1800459c1  mov     edx, 1
0x1800459c6  mov     rax, [rcx]
0x1800459c9  mov     rax, [rax+18h]
0x1800459cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459d2  mov     ebx, eax
0x1800459d4  test    eax, eax
0x1800459d6  jnz     loc_180045A72
0x1800459dc  mov     rcx, [rbp+arg_8]
0x1800459e0  lea     rdx, [rbp+pv]
0x1800459e4  mov     [rbp+pv], 0
0x1800459ec  mov     rax, [rcx]
0x1800459ef  mov     rax, [rax+20h]
0x1800459f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459f8  mov     ebx, eax
0x1800459fa  test    eax, eax
0x1800459fc  js      short loc_180045A52
0x1800459fe  mov     rcx, [rbp+pv]; unsigned __int16 *
0x180045a02  lea     rdx, [r14+rsi*8]; unsigned __int16 **
0x180045a06  call    ?CscUtil_CreateStringCopy@@YAJPEBGPEAPEAG@Z; CscUtil_CreateStringCopy(ushort const *,ushort * *)
0x180045a0b  mov     ebx, eax
0x180045a0d  test    eax, eax
0x180045a0f  js      short loc_180045A48
0x180045a11  inc     esi
0x180045a13  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a1a  lea     rax, WPP_GLOBAL_Control
0x180045a21  cmp     rcx, rax
0x180045a24  jz      short loc_180045A48
0x180045a26  test    dword ptr [rcx+1Ch], 2000000h
0x180045a2d  jz      short loc_180045A48
0x180045a2f  mov     r9, [rbp+pv]
0x180045a33  lea     r8, WPP_110f8852164937b701b00ed210f9da85_Traceguids
0x180045a3a  mov     rcx, [rcx+10h]
0x180045a3e  mov     edx, 0Dh
0x180045a43  call    WPP_SF_S
0x180045a48  mov     rcx, [rbp+pv]; pv
0x180045a4c  call    cs:__imp_CoTaskMemFree
0x180045a52  mov     rcx, [rbp+arg_8]
0x180045a56  mov     rax, [rcx]
0x180045a59  mov     rax, [rax+10h]
0x180045a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a62  mov     [rbp+arg_8], 0
0x180045a6a  test    ebx, ebx
0x180045a6c  jns     loc_1800459AD
0x180045a72  test    ebx, ebx
0x180045a74  jns     short loc_180045A95
0x180045a76  xor     esi, esi
0x180045a78  test    edi, edi
0x180045a7a  jz      short loc_180045A8B
0x180045a7c  mov     rcx, [r14+rsi*8]; lpMem
0x180045a80  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180045a85  inc     esi
0x180045a87  cmp     esi, edi
0x180045a89  jb      short loc_180045A7C
0x180045a8b  mov     rcx, r14; lpMem
0x180045a8e  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180045a93  jmp     short loc_180045A9C
0x180045a95  mov     [r12], r14
0x180045a99  mov     [r15], edi
0x180045a9c  mov     rcx, [rbp+arg_10]
0x180045aa0  mov     rax, [rcx]
0x180045aa3  mov     rax, [rax+10h]
0x180045aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045aac  mov     rcx, [rbp+var_10]
0x180045ab0  mov     rax, [rcx]
0x180045ab3  mov     rax, [rax+10h]
0x180045ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045abc  mov     eax, ebx
0x180045abe  add     rsp, 40h
0x180045ac2  pop     r15
0x180045ac4  pop     r14
0x180045ac6  pop     r12
0x180045ac8  pop     rdi
0x180045ac9  pop     rsi
0x180045aca  pop     rbx
0x180045acb  pop     rbp
0x180045acc  retn
```
