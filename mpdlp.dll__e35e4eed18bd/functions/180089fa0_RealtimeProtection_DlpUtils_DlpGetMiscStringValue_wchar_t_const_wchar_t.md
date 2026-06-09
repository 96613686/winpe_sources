# RealtimeProtection::DlpUtils::DlpGetMiscStringValue(wchar_t const *,wchar_t * *)

- ea: `0x180089fa0`
- end: `0x18008a0c6`
- name: `?DlpGetMiscStringValue@DlpUtils@RealtimeProtection@@YAJPEB_WPEAPEA_W@Z`
- size: `294`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpUtils *__hidden this, const wchar_t *, wchar_t **)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004fa30`
- `0x1800538c4`
- `0x1800857d0`
- `0x180186bd4`
- `0x18018d9f0`
- `0x180194970`
- `0x1801d6f7c`

## callees

- `0x180089fa0`
- `0x18010cb40`
- `0x1801458c0`
- `0x18023a290`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x18008a05f`
- `MpClient!MpFreeMemory` at `0x18008a083`
- `MpClient!MpFreeMemory` at `0x18008a05f`
- `MpClient!MpFreeMemory` at `0x18008a083`
- `MpClient!MpConfigClose` at `0x18008a030`
- `MpClient!MpConfigClose` at `0x18008a093`
- `MpClient!MpConfigClose` at `0x18008a0bb`
- `MpClient!MpConfigClose` at `0x18008a030`
- `MpClient!MpConfigClose` at `0x18008a093`
- `MpClient!MpConfigClose` at `0x18008a0bb`
- `MpClient!MpConfigOpen` at `0x18008a01a`
- `MpClient!MpConfigOpen` at `0x18008a01a`
- `MpClient!MpClientUtilExportFunctions` at `0x180089fca`
- `MpClient!MpClientUtilExportFunctions` at `0x180089fca`

## string_xrefs

- `0x18008a013`: `Miscellaneous Configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RealtimeProtection::DlpUtils::DlpGetMiscStringValue(
        RealtimeProtection::DlpUtils *this,
        wchar_t *a2,
        wchar_t **a3)
{
  __int64 v5; // rax
  __int64 v7; // rdx
  int v8; // esi
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rdx
  int ValueString; // edi
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // [rsp+20h] [rbp-38h] BYREF
  int v18; // [rsp+28h] [rbp-30h] BYREF
  __int64 v19; // [rsp+30h] [rbp-28h] BYREF

  *(_QWORD *)a2 = 0;
  v18 = 0;
  v5 = MpClientUtilExportFunctions(this, a2, a3);
  if ( (*(int (__fastcall **)(int *))(v5 + 152))(&v18) < 0 || !v18 )
    return 0;
  v17 = 0;
  v8 = MpConfigOpen(L"Miscellaneous Configuration", &v17);
  if ( v8 < 0 )
  {
    if ( v17 )
      MpConfigClose(v17, v7, v9, v10);
    return (unsigned int)v8;
  }
  v19 = 0;
  ValueString = MpConfigGetValueString(v17, this, &v19);
  if ( ValueString == -2147024894 )
  {
    if ( v19 )
      MpFreeMemory(v19);
    v15 = v17;
    if ( !v17 )
      return 0;
    goto LABEL_20;
  }
  if ( ValueString >= 0 )
  {
    v16 = v19;
    v19 = 0;
    *(_QWORD *)a2 = v16;
    v15 = v17;
    if ( !v17 )
      return 0;
LABEL_20:
    MpConfigClose(v15, v11, v13, v14);
    return 0;
  }
  if ( v19 )
    MpFreeMemory(v19);
  if ( v17 )
    MpConfigClose(v17, v11, v13, v14);
  return (unsigned int)ValueString;
}

```

## disassembly

```asm
0x180089fa0  mov     [rsp+arg_10], rbx
0x180089fa5  push    rbp
0x180089fa6  push    rsi
0x180089fa7  push    rdi
0x180089fa8  sub     rsp, 40h
0x180089fac  mov     rax, cs:__security_cookie
0x180089fb3  xor     rax, rsp
0x180089fb6  mov     [rsp+58h+var_20], rax
0x180089fbb  mov     rbx, rdx
0x180089fbe  mov     rdi, rcx
0x180089fc1  xor     ebp, ebp
0x180089fc3  mov     [rdx], rbp
0x180089fc6  mov     [rsp+58h+var_30], ebp
0x180089fca  call    cs:__imp_MpClientUtilExportFunctions
0x180089fd0  lea     rcx, [rsp+58h+var_30]
0x180089fd5  mov     rax, [rax+98h]
0x180089fdc  call    cs:__guard_dispatch_icall_fptr
0x180089fe2  nop
0x180089fe3  test    eax, eax
0x180089fe5  js      short loc_180089FED
0x180089fe7  cmp     [rsp+58h+var_30], ebp
0x180089feb  jnz     short loc_18008A009
0x180089fed  mov     eax, ebp
0x180089fef  mov     rcx, [rsp+58h+var_20]
0x180089ff4  xor     rcx, rsp; StackCookie
0x180089ff7  call    __security_check_cookie
0x180089ffc  mov     rbx, [rsp+58h+arg_10]
0x18008a001  add     rsp, 40h
0x18008a005  pop     rdi
0x18008a006  pop     rsi
0x18008a007  pop     rbp
0x18008a008  retn
0x18008a009  mov     [rsp+58h+var_38], rbp
0x18008a00e  lea     rdx, [rsp+58h+var_38]
0x18008a013  lea     rcx, aMiscellaneousC_0; "Miscellaneous Configuration"
0x18008a01a  call    cs:__imp_MpConfigOpen
0x18008a020  mov     esi, eax
0x18008a022  mov     rcx, [rsp+58h+var_38]
0x18008a027  test    eax, eax
0x18008a029  jns     short loc_18008A03A
0x18008a02b  test    rcx, rcx
0x18008a02e  jz      short loc_18008A036
0x18008a030  call    cs:__imp_MpConfigClose
0x18008a036  mov     eax, esi
0x18008a038  jmp     short loc_180089FEF
0x18008a03a  mov     [rsp+58h+var_28], rbp
0x18008a03f  lea     r8, [rsp+58h+var_28]
0x18008a044  mov     rdx, rdi
0x18008a047  call    MpConfigGetValueString
0x18008a04c  mov     edi, eax
0x18008a04e  cmp     eax, 80070002h
0x18008a053  jnz     short loc_18008A075
0x18008a055  mov     rcx, [rsp+58h+var_28]
0x18008a05a  test    rcx, rcx
0x18008a05d  jz      short loc_18008A065
0x18008a05f  call    cs:__imp_MpFreeMemory
0x18008a065  mov     rcx, [rsp+58h+var_38]
0x18008a06a  test    rcx, rcx
0x18008a06d  jz      loc_180089FED
0x18008a073  jmp     short loc_18008A0BB
0x18008a075  test    edi, edi
0x18008a077  jns     short loc_18008A0A0
0x18008a079  mov     rcx, [rsp+58h+var_28]
0x18008a07e  test    rcx, rcx
0x18008a081  jz      short loc_18008A089
0x18008a083  call    cs:__imp_MpFreeMemory
0x18008a089  mov     rcx, [rsp+58h+var_38]
0x18008a08e  test    rcx, rcx
0x18008a091  jz      short loc_18008A099
0x18008a093  call    cs:__imp_MpConfigClose
0x18008a099  mov     eax, edi
0x18008a09b  jmp     loc_180089FEF
0x18008a0a0  mov     rax, [rsp+58h+var_28]
0x18008a0a5  mov     [rsp+58h+var_28], rbp
0x18008a0aa  mov     [rbx], rax
0x18008a0ad  mov     rcx, [rsp+58h+var_38]
0x18008a0b2  test    rcx, rcx
0x18008a0b5  jz      loc_180089FED
0x18008a0bb  call    cs:__imp_MpConfigClose
0x18008a0c1  jmp     loc_180089FED
```
