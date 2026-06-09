# NgcUtils::DoesTPMSupportNgcIso(void)

- ea: `0x180043444`
- end: `0x180043513`
- name: `?DoesTPMSupportNgcIso@NgcUtils@@YA_NXZ`
- size: `207`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800433ec`

## callees

- `0x180043444`
- `0x1800438d4`
- `0x180043918`
- `0x180046ce0`

## import_xrefs

- `tbs!Tbsi_GetDeviceInfo` at `0x180043469`
- `tbs!Tbsi_GetDeviceInfo` at `0x180043469`

## string_xrefs

- `0x180043474`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x1800434b3`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x1800434d6`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

## pseudocode

```c
char __fastcall NgcUtils::DoesTPMSupportNgcIso(NgcUtils *this)
{
  unsigned int DeviceInfo; // eax
  char *v3; // [rsp+28h] [rbp-30h]
  char *v4[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_OWORD *)v4 = 0;
  DeviceInfo = Tbsi_GetDeviceInfo(16, v4);
  if ( wil::details::in1diag3::Log_IfFailedWithExpected(
         retaddr,
         (void *)0x8E,
         (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
         (const char *)DeviceInfo,
         1,
         0x8028400F) < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)0x80090029LL,
      (int)"TPM not found in the device",
      v3);
    return 0;
  }
  if ( HIDWORD(v4[0]) < 2 )
  {
    LODWORD(v3) = HIDWORD(v4[0]);
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)0x80090029LL,
      (int)"TPM version %d is not supported for NgcIso.",
      v3);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180043444  sub     rsp, 58h
0x180043448  mov     rax, cs:__security_cookie
0x18004344f  xor     rax, rsp
0x180043452  mov     [rsp+58h+var_18], rax
0x180043457  xorps   xmm0, xmm0
0x18004345a  lea     rdx, [rsp+58h+var_28]
0x18004345f  mov     ecx, 10h
0x180043464  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x180043469  call    cs:__imp_Tbsi_GetDeviceInfo
0x18004346f  mov     rcx, [rsp+58h]; this
0x180043474  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18004347b  mov     r9d, eax; char *
0x18004347e  mov     dword ptr [rsp+58h+var_30], 8028400Fh; char *
0x180043486  mov     edx, 8Eh; void *
0x18004348b  mov     [rsp+58h+var_38], 1; int
0x180043493  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180043498  test    eax, eax
0x18004349a  jns     short loc_1800434C8
0x18004349c  mov     rcx, [rsp+58h]; this
0x1800434a1  lea     rax, aTpmNotFoundInT; "TPM not found in the device"
0x1800434a8  mov     r9d, 80090029h; char *
0x1800434ae  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800434b3  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800434ba  mov     edx, 90h; void *
0x1800434bf  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800434c4  xor     al, al
0x1800434c6  jmp     short loc_180043501
0x1800434c8  mov     eax, dword ptr [rsp+58h+var_28+4]
0x1800434cc  cmp     eax, 2
0x1800434cf  jnb     short loc_1800434FF
0x1800434d1  mov     rcx, [rsp+58h]; this
0x1800434d6  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800434dd  mov     dword ptr [rsp+58h+var_30], eax; char *
0x1800434e1  mov     r9d, 80090029h; char *
0x1800434e7  lea     rax, aTpmVersionDIsN; "TPM version %d is not supported for Ngc"...
0x1800434ee  mov     edx, 96h; void *
0x1800434f3  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800434f8  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800434fd  jmp     short loc_1800434C4
0x1800434ff  mov     al, 1
0x180043501  mov     rcx, [rsp+58h+var_18]
0x180043506  xor     rcx, rsp; StackCookie
0x180043509  call    __security_check_cookie
0x18004350e  add     rsp, 58h
0x180043512  retn
```
