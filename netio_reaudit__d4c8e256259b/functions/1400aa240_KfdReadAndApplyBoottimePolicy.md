# KfdReadAndApplyBoottimePolicy

- ea: `0x1400aa240`
- end: `0x1400aa2e4`
- name: `KfdReadAndApplyBoottimePolicy`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400aa16c`

## callees

- `0x140009520`
- `0x140009e00`
- `0x140061abc`
- `0x140078400`
- `0x1400aa240`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400aa288`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400aa288`

## string_xrefs

- `0x1400aa2af`: `RtlQueryRegistryValuesEx`
- `0x1400aa2c8`: `KfdReadAndApplyBoottimePolicy`

## pseudocode

```c
__int64 KfdReadAndApplyBoottimePolicy()
{
  __int64 v0; // rbx
  unsigned int v1; // eax
  __int64 (__fastcall *v3)(); // [rsp+30h] [rbp-78h] BYREF
  int v4; // [rsp+38h] [rbp-70h]
  _BYTE v5[100]; // [rsp+3Ch] [rbp-6Ch] BYREF

  v0 = 0;
  memset(v5, 0, sizeof(v5));
  v4 = 16;
  v3 = KfdApplyBoottimePolicyCallback;
  v1 = RtlQueryRegistryValuesEx(2147483649LL, L"BFE\\Parameters\\Policy\\BootTime\\Filter", &v3, 0, 0);
  if ( (int)(v1 + 0x80000000) >= 0 && v1 != -1073741772 )
  {
    v0 = WfpReportSysErrorAsNtStatus(0x80000000LL, "RtlQueryRegistryValuesEx", v1, 1);
    if ( v0 )
    {
      KfdDestroyBoottimePolicy();
      WfpReportError(v0, "KfdReadAndApplyBoottimePolicy");
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1400aa240  push    rbx
0x1400aa242  sub     rsp, 0A0h
0x1400aa249  xor     ebx, ebx
0x1400aa24b  lea     rcx, [rsp+0A8h+var_6C]; void *
0x1400aa250  xor     edx, edx; Val
0x1400aa252  lea     r8d, [rbx+64h]; Size
0x1400aa256  call    memset
0x1400aa25b  lea     rax, KfdApplyBoottimePolicyCallback
0x1400aa262  mov     [rsp+0A8h+var_70], 10h
0x1400aa26a  xor     r9d, r9d
0x1400aa26d  mov     [rsp+0A8h+var_78], rax
0x1400aa272  lea     r8, [rsp+0A8h+var_78]
0x1400aa277  mov     [rsp+0A8h+var_88], rbx
0x1400aa27c  lea     rdx, aBfeParametersP; "BFE\\Parameters\\Policy\\BootTime\\Filt"...
0x1400aa283  mov     ecx, 80000001h
0x1400aa288  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400aa28f  nop     dword ptr [rax+rax+00h]
0x1400aa294  mov     ecx, 80000000h
0x1400aa299  mov     r8d, eax
0x1400aa29c  add     eax, ecx
0x1400aa29e  test    ecx, eax
0x1400aa2a0  jnz     short loc_1400AA2D7
0x1400aa2a2  cmp     r8d, 0C0000034h
0x1400aa2a9  jz      short loc_1400AA2D7
0x1400aa2ab  lea     r9d, [rbx+1]
0x1400aa2af  lea     rdx, aRtlqueryregist_0; "RtlQueryRegistryValuesEx"
0x1400aa2b6  call    WfpReportSysErrorAsNtStatus
0x1400aa2bb  mov     rbx, rax
0x1400aa2be  test    rax, rax
0x1400aa2c1  jz      short loc_1400AA2D7
0x1400aa2c3  call    KfdDestroyBoottimePolicy
0x1400aa2c8  lea     rdx, aKfdreadandappl; "KfdReadAndApplyBoottimePolicy"
0x1400aa2cf  mov     rcx, rbx
0x1400aa2d2  call    WfpReportError
0x1400aa2d7  mov     rax, rbx
0x1400aa2da  add     rsp, 0A0h
0x1400aa2e1  pop     rbx
0x1400aa2e2  retn
```
