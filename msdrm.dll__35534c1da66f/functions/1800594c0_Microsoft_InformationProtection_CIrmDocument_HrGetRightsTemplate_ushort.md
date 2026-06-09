# Microsoft::InformationProtection::CIrmDocument::HrGetRightsTemplate(ushort * *)

- ea: `0x1800594c0`
- end: `0x180059553`
- name: `?HrGetRightsTemplate@CIrmDocument@InformationProtection@Microsoft@@UEAAJPEAPEAG@Z`
- size: `147`
- prototype: `__int64 __fastcall(Microsoft::InformationProtection::CIrmDocument *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800594c0`
- `0x18005a9cc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180059511`
- `OLEAUT32!__imp_SysAllocString` at `0x180059511`

## string_xrefs

- `0x1800594d7`: `Microsoft::InformationProtection::CIrmDocument::HrGetRightsTemplate`
- `0x18005952d`: `Microsoft::InformationProtection::CIrmDocument::HrGetRightsTemplate`

## pseudocode

```c
__int64 __fastcall Microsoft::InformationProtection::CIrmDocument::HrGetRightsTemplate(
        Microsoft::InformationProtection::CIrmDocument *this,
        unsigned __int16 **a2)
{
  int v4; // ebx
  unsigned __int16 *v5; // rax

  if ( !a2 )
  {
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"%S Exited with hr = 0x%x",
      "Microsoft::InformationProtection::CIrmDocument::HrGetRightsTemplate",
      2147942487LL);
    return 2147942487LL;
  }
  if ( *((_DWORD *)this + 3) && *((_QWORD *)this + 16) )
    v4 = 0;
  else
    v4 = -2147418113;
  v5 = SysAllocString(*((const OLECHAR **)this + 16));
  if ( !v5 )
  {
    v4 = -2147024882;
LABEL_10:
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"%S FAILED at Line %d with hr = 0x%x",
      "Microsoft::InformationProtection::CIrmDocument::HrGetRightsTemplate",
      486,
      (unsigned int)v4);
    return 0;
  }
  *a2 = v5;
  if ( v4 < 0 )
    goto LABEL_10;
  return 0;
}

```

## disassembly

```asm
0x1800594c0  mov     [rsp+arg_0], rbx
0x1800594c5  push    rdi
0x1800594c6  sub     rsp, 20h
0x1800594ca  mov     rdi, rdx
0x1800594cd  test    rdx, rdx
0x1800594d0  jnz     short loc_1800594F1
0x1800594d2  mov     ebx, 80070057h
0x1800594d7  lea     rdx, aMicrosoftInfor_25; "Microsoft::InformationProtection::CIrmD"...
0x1800594de  mov     r8d, ebx
0x1800594e1  lea     rcx, aSExitedWithHr0; "%S Exited with hr = 0x%x"
0x1800594e8  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x1800594ed  mov     eax, ebx
0x1800594ef  jmp     short loc_180059548
0x1800594f1  cmp     dword ptr [rcx+0Ch], 0
0x1800594f5  jz      short loc_180059505
0x1800594f7  cmp     qword ptr [rcx+80h], 0
0x1800594ff  jz      short loc_180059505
0x180059501  xor     ebx, ebx
0x180059503  jmp     short loc_18005950A
0x180059505  mov     ebx, 8000FFFFh
0x18005950a  mov     rcx, [rcx+80h]; psz
0x180059511  call    cs:__imp_SysAllocString
0x180059517  test    rax, rax
0x18005951a  jnz     short loc_180059523
0x18005951c  mov     ebx, 8007000Eh
0x180059521  jmp     short loc_18005952A
0x180059523  mov     [rdi], rax
0x180059526  test    ebx, ebx
0x180059528  jns     short loc_180059546
0x18005952a  mov     r9d, ebx
0x18005952d  lea     rdx, aMicrosoftInfor_25; "Microsoft::InformationProtection::CIrmD"...
0x180059534  mov     r8d, 1E6h
0x18005953a  lea     rcx, aSFailedAtLineD; "%S FAILED at Line %d with hr = 0x%x"
0x180059541  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x180059546  xor     eax, eax
0x180059548  mov     rbx, [rsp+28h+arg_0]
0x18005954d  add     rsp, 20h
0x180059551  pop     rdi
0x180059552  retn
```
