# CRepository::GetLogonTemplate(ulong,ulong,__MIDL___MIDL_itf_reposit_0001_0003_0002 * *)

- ea: `0x180039b80`
- end: `0x180039c6b`
- name: `?GetLogonTemplate@CRepository@@UEAAJKKPEAPEAU__MIDL___MIDL_itf_reposit_0001_0003_0002@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(CRepository *this, __int64, __int64, struct __MIDL___MIDL_itf_reposit_0001_0003_0002 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800012b8`
- `0x180039b80`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180039c09`
- `wbemcomn!GetMemLogObject` at `0x180039c09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039c19`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039c19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039bfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039c03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039bfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039c03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039b97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039ba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039b97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039ba5`
- `OLEAUT32!__imp_VariantInit` at `0x180039bcc`
- `OLEAUT32!__imp_VariantInit` at `0x180039bcc`

## pseudocode

```c
__int64 __fastcall CRepository::GetLogonTemplate(
        CRepository *this,
        __int64 a2,
        __int64 a3,
        struct __MIDL___MIDL_itf_reposit_0001_0003_0002 **a4)
{
  struct __MIDL___MIDL_itf_reposit_0001_0003_0002 *v5; // rdi
  char *v6; // rax
  char *v7; // rbx
  __int64 result; // rax
  CMemoryLog *MemLogObject; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF

  v5 = (struct __MIDL___MIDL_itf_reposit_0001_0003_0002 *)CoTaskMemAlloc(0x10u);
  v6 = (char *)CoTaskMemAlloc(0x28u);
  v7 = v6;
  if ( v5 && v6 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    result = 0;
    *(VARIANTARG *)(v7 + 16) = pvarg;
    *(_DWORD *)v5 = 1;
    *((_QWORD *)v5 + 1) = v7;
    *a4 = v5;
  }
  else
  {
    CoTaskMemFree(v5);
    CoTaskMemFree(v7);
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x180039b80  mov     [rsp+arg_0], rbx
0x180039b85  mov     [rsp+arg_8], rsi
0x180039b8a  push    rdi
0x180039b8b  sub     rsp, 40h
0x180039b8f  mov     ecx, 10h; cb
0x180039b94  mov     rsi, r9
0x180039b97  call    cs:__imp_CoTaskMemAlloc
0x180039b9d  mov     ecx, 28h ; '('; cb
0x180039ba2  mov     rdi, rax
0x180039ba5  call    cs:__imp_CoTaskMemAlloc
0x180039bab  mov     rbx, rax
0x180039bae  test    rdi, rdi
0x180039bb1  jz      short loc_180039BF7
0x180039bb3  test    rax, rax
0x180039bb6  jz      short loc_180039BF7
0x180039bb8  xorps   xmm0, xmm0
0x180039bbb  lea     rcx, [rsp+48h+pvarg]; pvarg
0x180039bc0  xor     eax, eax
0x180039bc2  movups  xmmword ptr [rsp+48h+pvarg], xmm0
0x180039bc7  mov     qword ptr [rsp+48h+pvarg+10h], rax
0x180039bcc  call    cs:__imp_VariantInit
0x180039bd2  movups  xmm0, xmmword ptr [rsp+48h+pvarg]
0x180039bd7  xor     eax, eax
0x180039bd9  movups  xmmword ptr [rbx+10h], xmm0
0x180039bdd  movsd   xmm1, qword ptr [rsp+48h+pvarg+10h]
0x180039be3  movsd   qword ptr [rbx+20h], xmm1
0x180039be8  mov     dword ptr [rdi], 1
0x180039bee  mov     [rdi+8], rbx
0x180039bf2  mov     [rsi], rdi
0x180039bf5  jmp     short loc_180039C5B
0x180039bf7  mov     rcx, rdi; pv
0x180039bfa  call    cs:__imp_CoTaskMemFree
0x180039c00  mov     rcx, rbx; pv
0x180039c03  call    cs:__imp_CoTaskMemFree
0x180039c09  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180039c0f  mov     ebx, 80041006h
0x180039c14  mov     rcx, rax
0x180039c17  mov     edx, ebx
0x180039c19  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180039c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c26  lea     rax, WPP_GLOBAL_Control
0x180039c2d  cmp     rcx, rax
0x180039c30  jz      short loc_180039C59
0x180039c32  test    byte ptr [rcx+1Ch], 1
0x180039c36  jz      short loc_180039C59
0x180039c38  cmp     byte ptr [rcx+19h], 2
0x180039c3c  jb      short loc_180039C59
0x180039c3e  mov     rcx, [rcx+10h]
0x180039c42  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x180039c49  mov     edx, 43h ; 'C'
0x180039c4e  mov     r9d, 80041006h
0x180039c54  call    WPP_SF_d
0x180039c59  mov     eax, ebx
0x180039c5b  mov     rbx, [rsp+48h+arg_0]
0x180039c60  mov     rsi, [rsp+48h+arg_8]
0x180039c65  add     rsp, 40h
0x180039c69  pop     rdi
0x180039c6a  retn
```
