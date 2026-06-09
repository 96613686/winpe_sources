# FF_GetDumpProperties(_GUID * *,int *,ushort * *,ulong *)

- ea: `0x18000f0bc`
- end: `0x18000f2b1`
- name: `?FF_GetDumpProperties@@YAJPEAPEAU_GUID@@PEAHPEAPEAGPEAK@Z`
- size: `501`
- prototype: `__int64 __fastcall(struct _GUID **, int *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ee14`

## callees

- `0x18000f0bc`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x18000f104`
- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x18000f104`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f269`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f269`

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
0x18000f0bc  mov     rax, rsp
0x18000f0bf  mov     [rax+18h], r8
0x18000f0c3  push    rbx
0x18000f0c4  push    rsi
0x18000f0c5  push    rdi
0x18000f0c6  push    r12
0x18000f0c8  push    r14
0x18000f0ca  push    r15
0x18000f0cc  sub     rsp, 68h
0x18000f0d0  mov     r14, r9
0x18000f0d3  mov     rdi, r8
0x18000f0d6  mov     rsi, rdx
0x18000f0d9  mov     rbx, rcx
0x18000f0dc  mov     r12d, 80004005h
0x18000f0e2  mov     [rax-68h], r12d
0x18000f0e6  xor     r15d, r15d
0x18000f0e9  mov     [rax-40h], r15
0x18000f0ed  mov     [rax-48h], r15
0x18000f0f1  mov     [rax-58h], r15
0x18000f0f5  mov     [rax-60h], r15d
0x18000f0f9  lea     rdx, [rax-48h]; ppv
0x18000f0fd  lea     rcx, _GUID_000001c6_0000_0000_c000_000000000046; riid
0x18000f104  call    cs:__imp_CoGetObjectContext
0x18000f10a  mov     [rsp+98h+var_68], eax
0x18000f10e  test    eax, eax
0x18000f110  js      short loc_18000F16A
0x18000f112  mov     rcx, [rsp+98h+var_48]
0x18000f117  mov     rax, [rcx]
0x18000f11a  lea     r9, [rsp+98h+var_40]
0x18000f11f  lea     r8, [rsp+98h+var_60]
0x18000f124  lea     rdx, guidApplicationInfo
0x18000f12b  mov     rax, [rax+28h]
0x18000f12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f134  mov     [rsp+98h+var_68], eax
0x18000f138  test    eax, eax
0x18000f13a  js      short loc_18000F16A
0x18000f13c  mov     rcx, [rsp+98h+var_40]
0x18000f141  test    rcx, rcx
0x18000f144  jz      short loc_18000F16A
0x18000f146  mov     rax, [rcx]
0x18000f149  lea     r8, [rsp+98h+var_58]
0x18000f14e  lea     rdx, _GUID_000001e3_0000_0000_c000_000000000046
0x18000f155  mov     rax, [rax]
0x18000f158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f15d  mov     [rsp+98h+var_68], eax
0x18000f161  test    eax, eax
0x18000f163  jns     short loc_18000F16A
0x18000f165  mov     [rsp+98h+var_58], r15
0x18000f16a  cmp     [rsp+98h+var_58], r15
0x18000f16f  jnz     short loc_18000F193
0x18000f171  mov     rcx, cs:?g_pFailfastIComApplInfo2@@3PEAUIComApplInfo2@@EA; IComApplInfo2 * g_pFailfastIComApplInfo2
0x18000f178  mov     [rsp+98h+var_58], rcx
0x18000f17d  cmp     rcx, r15
0x18000f180  jnz     short loc_18000F193
0x18000f182  mov     eax, r12d
0x18000f185  add     rsp, 68h
0x18000f189  pop     r15
0x18000f18b  pop     r14
0x18000f18d  pop     r12
0x18000f18f  pop     rdi
0x18000f190  pop     rsi
0x18000f191  pop     rbx
0x18000f192  retn
0x18000f193  mov     rcx, [rsp+98h+var_58]
0x18000f198  mov     rax, [rcx]
0x18000f19b  mov     rdx, rbx
0x18000f19e  mov     rax, [rax+18h]
0x18000f1a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1a7  mov     ebx, eax
0x18000f1a9  mov     [rsp+98h+var_68], eax
0x18000f1ad  test    eax, eax
0x18000f1af  js      short loc_18000F210
0x18000f1b1  mov     rcx, [rsp+98h+var_58]
0x18000f1b6  mov     rax, [rcx]
0x18000f1b9  mov     rdx, rsi
0x18000f1bc  mov     rax, [rax+0E0h]
0x18000f1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1c8  mov     ebx, eax
0x18000f1ca  mov     [rsp+98h+var_68], eax
0x18000f1ce  test    eax, eax
0x18000f1d0  js      short loc_18000F210
0x18000f1d2  mov     rcx, [rsp+98h+var_58]
0x18000f1d7  mov     rax, [rcx]
0x18000f1da  mov     rdx, rdi
0x18000f1dd  mov     rax, [rax+0F0h]
0x18000f1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1e9  mov     ebx, eax
0x18000f1eb  mov     [rsp+98h+var_68], eax
0x18000f1ef  test    eax, eax
0x18000f1f1  js      short loc_18000F210
0x18000f1f3  mov     rcx, [rsp+98h+var_58]
0x18000f1f8  mov     rax, [rcx]
0x18000f1fb  mov     rdx, r14
0x18000f1fe  mov     rax, [rax+0E8h]
0x18000f205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f20a  mov     ebx, eax
0x18000f20c  mov     [rsp+98h+var_68], eax
0x18000f210  test    ebx, ebx
0x18000f212  js      short loc_18000F21F
0x18000f214  cmp     [rdi], r15
0x18000f217  cmovz   ebx, r12d
0x18000f21b  mov     [rsp+98h+var_68], ebx
0x18000f21f  mov     [rsp+98h+var_64], r15d
0x18000f224  mov     rcx, [rsp+98h+var_58]
0x18000f229  mov     rax, [rcx]
0x18000f22c  lea     rdx, [rsp+98h+var_64]
0x18000f231  mov     rax, [rax+28h]
0x18000f235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f23a  cmp     [rsi], r15d
0x18000f23d  jnz     short loc_18000F2AA
0x18000f23f  cmp     [rsp+98h+var_64], r15d
0x18000f244  jz      short loc_18000F2AA
0x18000f246  mov     [rsp+98h+var_50], r15
0x18000f24b  lea     rax, [rsp+98h+var_50]
0x18000f250  mov     [rsp+98h+ppv], rax; ppv
0x18000f255  lea     r9, IID_IDumpControl; riid
0x18000f25c  xor     edx, edx; pUnkOuter
0x18000f25e  lea     r8d, [rdx+1]; dwClsContext
0x18000f262  lea     rcx, CLSID_MTSPackage; rclsid
0x18000f269  call    cs:__imp_CoCreateInstance
0x18000f26f  mov     ebx, eax
0x18000f271  mov     [rsp+98h+var_68], eax
0x18000f275  test    eax, eax
0x18000f277  js      short loc_18000F2AA
0x18000f279  mov     rcx, [rsp+98h+var_50]
0x18000f27e  mov     rax, [rcx]
0x18000f281  mov     r9, r14
0x18000f284  mov     r8, rdi
0x18000f287  mov     rdx, rsi
0x18000f28a  mov     rax, [rax+18h]
0x18000f28e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f293  mov     ebx, eax
0x18000f295  mov     [rsp+98h+var_68], eax
0x18000f299  mov     rcx, [rsp+98h+var_50]
0x18000f29e  mov     rax, [rcx]
0x18000f2a1  mov     rax, [rax+10h]
0x18000f2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2aa  mov     eax, ebx
0x18000f2ac  jmp     loc_18000F185
0x180014332  push    rbp
0x180014334  sub     rsp, 30h
0x180014338  mov     rbp, rdx
0x18001433b  add     rsp, 30h
0x18001433f  pop     rbp
0x180014340  retn
0x180014342  push    rbp
0x180014344  sub     rsp, 30h
0x180014348  mov     rbp, rdx
0x18001434b  mov     ecx, [rbp+30h]
0x18001434e  test    ecx, ecx
0x180014350  js      short loc_180014368
0x180014352  mov     edx, 80004005h
0x180014357  mov     rax, [rbp+0B0h]
0x18001435e  cmp     qword ptr [rax], 0
0x180014362  cmovz   ecx, edx
0x180014365  mov     [rbp+30h], ecx
0x180014368  add     rsp, 30h
0x18001436c  pop     rbp
0x18001436d  retn
```
