# FF_GetDumpProperties(_GUID * *,int *,ushort * *,ulong *)

- ea: `0x140003a54`
- end: `0x140003c49`
- name: `?FF_GetDumpProperties@@YAJPEAPEAU_GUID@@PEAHPEAPEAGPEAK@Z`
- size: `501`
- prototype: `__int64 __fastcall(struct _GUID **, int *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400037ac`

## callees

- `0x140003a54`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003c01`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003c01`
- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x140003a9c`
- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x140003a9c`

## pseudocode

```c
__int64 __fastcall FF_GetDumpProperties(struct _GUID **a1, int *a2, unsigned __int16 **a3, unsigned int *a4)
{
  HRESULT v9; // ebx
  int v10; // [rsp+34h] [rbp-64h] BYREF
  int v11; // [rsp+38h] [rbp-60h] BYREF
  struct IComApplInfo2 *v12; // [rsp+40h] [rbp-58h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-50h] BYREF
  LPVOID v14; // [rsp+50h] [rbp-48h] BYREF
  int (__fastcall ***v15)(_QWORD, GUID *, struct IComApplInfo2 **); // [rsp+58h] [rbp-40h] BYREF

  v15 = 0;
  v14 = 0;
  v12 = 0;
  v11 = 0;
  if ( CoGetObjectContext(&GUID_000001c6_0000_0000_c000_000000000046, &v14) >= 0
    && (*(int (__fastcall **)(LPVOID, __int64 *, int *, int (__fastcall ****)(_QWORD, GUID *, struct IComApplInfo2 **)))(*(_QWORD *)v14 + 40LL))(
         v14,
         guidApplicationInfo,
         &v11,
         &v15) >= 0
    && v15
    && (**v15)(v15, &GUID_000001e3_0000_0000_c000_000000000046, &v12) < 0 )
  {
    v12 = 0;
  }
  if ( !v12 )
  {
    v12 = g_pFailfastIComApplInfo2;
    if ( !g_pFailfastIComApplInfo2 )
      return 2147500037LL;
  }
  v9 = (*(__int64 (__fastcall **)(struct IComApplInfo2 *, struct _GUID **))(*(_QWORD *)v12 + 24LL))(v12, a1);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(struct IComApplInfo2 *, int *))(*(_QWORD *)v12 + 224LL))(v12, a2);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct IComApplInfo2 *, unsigned __int16 **))(*(_QWORD *)v12 + 240LL))(v12, a3);
      if ( v9 >= 0 )
        v9 = (*(__int64 (__fastcall **)(struct IComApplInfo2 *, unsigned int *))(*(_QWORD *)v12 + 232LL))(v12, a4);
    }
  }
  if ( v9 >= 0 && !*a3 )
    v9 = -2147467259;
  v10 = 0;
  (*(void (__fastcall **)(struct IComApplInfo2 *, int *))(*(_QWORD *)v12 + 40LL))(v12, &v10);
  if ( !*a2 && v10 )
  {
    ppv = 0;
    v9 = CoCreateInstance(&CLSID_MTSPackage, 0, 1u, &IID_IDumpControl, &ppv);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(LPVOID, int *, unsigned __int16 **, unsigned int *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             a2,
             a3,
             a4);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140003a54  mov     rax, rsp
0x140003a57  mov     [rax+18h], r8
0x140003a5b  push    rbx
0x140003a5c  push    rsi
0x140003a5d  push    rdi
0x140003a5e  push    r12
0x140003a60  push    r14
0x140003a62  push    r15
0x140003a64  sub     rsp, 68h
0x140003a68  mov     r14, r9
0x140003a6b  mov     rdi, r8
0x140003a6e  mov     rsi, rdx
0x140003a71  mov     rbx, rcx
0x140003a74  mov     r12d, 80004005h
0x140003a7a  mov     [rax-68h], r12d
0x140003a7e  xor     r15d, r15d
0x140003a81  mov     [rax-40h], r15
0x140003a85  mov     [rax-48h], r15
0x140003a89  mov     [rax-58h], r15
0x140003a8d  mov     [rax-60h], r15d
0x140003a91  lea     rdx, [rax-48h]; ppv
0x140003a95  lea     rcx, _GUID_000001c6_0000_0000_c000_000000000046; riid
0x140003a9c  call    cs:__imp_CoGetObjectContext
0x140003aa2  mov     [rsp+98h+var_68], eax
0x140003aa6  test    eax, eax
0x140003aa8  js      short loc_140003B02
0x140003aaa  mov     rcx, [rsp+98h+var_48]
0x140003aaf  mov     rax, [rcx]
0x140003ab2  lea     r9, [rsp+98h+var_40]
0x140003ab7  lea     r8, [rsp+98h+var_60]
0x140003abc  lea     rdx, guidApplicationInfo
0x140003ac3  mov     rax, [rax+28h]
0x140003ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003acc  mov     [rsp+98h+var_68], eax
0x140003ad0  test    eax, eax
0x140003ad2  js      short loc_140003B02
0x140003ad4  mov     rcx, [rsp+98h+var_40]
0x140003ad9  test    rcx, rcx
0x140003adc  jz      short loc_140003B02
0x140003ade  mov     rax, [rcx]
0x140003ae1  lea     r8, [rsp+98h+var_58]
0x140003ae6  lea     rdx, _GUID_000001e3_0000_0000_c000_000000000046
0x140003aed  mov     rax, [rax]
0x140003af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003af5  mov     [rsp+98h+var_68], eax
0x140003af9  test    eax, eax
0x140003afb  jns     short loc_140003B02
0x140003afd  mov     [rsp+98h+var_58], r15
0x140003b02  cmp     [rsp+98h+var_58], r15
0x140003b07  jnz     short loc_140003B2B
0x140003b09  mov     rcx, cs:?g_pFailfastIComApplInfo2@@3PEAUIComApplInfo2@@EA; IComApplInfo2 * g_pFailfastIComApplInfo2
0x140003b10  mov     [rsp+98h+var_58], rcx
0x140003b15  cmp     rcx, r15
0x140003b18  jnz     short loc_140003B2B
0x140003b1a  mov     eax, r12d
0x140003b1d  add     rsp, 68h
0x140003b21  pop     r15
0x140003b23  pop     r14
0x140003b25  pop     r12
0x140003b27  pop     rdi
0x140003b28  pop     rsi
0x140003b29  pop     rbx
0x140003b2a  retn
0x140003b2b  mov     rcx, [rsp+98h+var_58]
0x140003b30  mov     rax, [rcx]
0x140003b33  mov     rdx, rbx
0x140003b36  mov     rax, [rax+18h]
0x140003b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b3f  mov     ebx, eax
0x140003b41  mov     [rsp+98h+var_68], eax
0x140003b45  test    eax, eax
0x140003b47  js      short loc_140003BA8
0x140003b49  mov     rcx, [rsp+98h+var_58]
0x140003b4e  mov     rax, [rcx]
0x140003b51  mov     rdx, rsi
0x140003b54  mov     rax, [rax+0E0h]
0x140003b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b60  mov     ebx, eax
0x140003b62  mov     [rsp+98h+var_68], eax
0x140003b66  test    eax, eax
0x140003b68  js      short loc_140003BA8
0x140003b6a  mov     rcx, [rsp+98h+var_58]
0x140003b6f  mov     rax, [rcx]
0x140003b72  mov     rdx, rdi
0x140003b75  mov     rax, [rax+0F0h]
0x140003b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b81  mov     ebx, eax
0x140003b83  mov     [rsp+98h+var_68], eax
0x140003b87  test    eax, eax
0x140003b89  js      short loc_140003BA8
0x140003b8b  mov     rcx, [rsp+98h+var_58]
0x140003b90  mov     rax, [rcx]
0x140003b93  mov     rdx, r14
0x140003b96  mov     rax, [rax+0E8h]
0x140003b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ba2  mov     ebx, eax
0x140003ba4  mov     [rsp+98h+var_68], eax
0x140003ba8  test    ebx, ebx
0x140003baa  js      short loc_140003BB7
0x140003bac  cmp     [rdi], r15
0x140003baf  cmovz   ebx, r12d
0x140003bb3  mov     [rsp+98h+var_68], ebx
0x140003bb7  mov     [rsp+98h+var_64], r15d
0x140003bbc  mov     rcx, [rsp+98h+var_58]
0x140003bc1  mov     rax, [rcx]
0x140003bc4  lea     rdx, [rsp+98h+var_64]
0x140003bc9  mov     rax, [rax+28h]
0x140003bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bd2  cmp     [rsi], r15d
0x140003bd5  jnz     short loc_140003C42
0x140003bd7  cmp     [rsp+98h+var_64], r15d
0x140003bdc  jz      short loc_140003C42
0x140003bde  mov     [rsp+98h+var_50], r15
0x140003be3  lea     rax, [rsp+98h+var_50]
0x140003be8  mov     [rsp+98h+ppv], rax; ppv
0x140003bed  lea     r9, IID_IDumpControl; riid
0x140003bf4  xor     edx, edx; pUnkOuter
0x140003bf6  lea     r8d, [rdx+1]; dwClsContext
0x140003bfa  lea     rcx, CLSID_MTSPackage; rclsid
0x140003c01  call    cs:__imp_CoCreateInstance
0x140003c07  mov     ebx, eax
0x140003c09  mov     [rsp+98h+var_68], eax
0x140003c0d  test    eax, eax
0x140003c0f  js      short loc_140003C42
0x140003c11  mov     rcx, [rsp+98h+var_50]
0x140003c16  mov     rax, [rcx]
0x140003c19  mov     r9, r14
0x140003c1c  mov     r8, rdi
0x140003c1f  mov     rdx, rsi
0x140003c22  mov     rax, [rax+18h]
0x140003c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c2b  mov     ebx, eax
0x140003c2d  mov     [rsp+98h+var_68], eax
0x140003c31  mov     rcx, [rsp+98h+var_50]
0x140003c36  mov     rax, [rcx]
0x140003c39  mov     rax, [rax+10h]
0x140003c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c42  mov     eax, ebx
0x140003c44  jmp     loc_140003B1D
0x1400070ad  push    rbp
0x1400070af  sub     rsp, 30h
0x1400070b3  mov     rbp, rdx
0x1400070b6  add     rsp, 30h
0x1400070ba  pop     rbp
0x1400070bb  retn
0x1400070bd  push    rbp
0x1400070bf  sub     rsp, 30h
0x1400070c3  mov     rbp, rdx
0x1400070c6  mov     ecx, [rbp+30h]
0x1400070c9  test    ecx, ecx
0x1400070cb  js      short loc_1400070E3
0x1400070cd  mov     edx, 80004005h
0x1400070d2  mov     rax, [rbp+0B0h]
0x1400070d9  cmp     qword ptr [rax], 0
0x1400070dd  cmovz   ecx, edx
0x1400070e0  mov     [rbp+30h], ecx
0x1400070e3  add     rsp, 30h
0x1400070e7  pop     rbp
0x1400070e8  retn
```
