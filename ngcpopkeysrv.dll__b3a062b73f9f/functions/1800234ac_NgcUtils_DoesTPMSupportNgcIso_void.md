# NgcUtils::DoesTPMSupportNgcIso(void)

- ea: `0x1800234ac`
- end: `0x18002357b`
- name: `?DoesTPMSupportNgcIso@NgcUtils@@YA_NXZ`
- size: `207`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180023454`

## callees

- `0x180004de0`
- `0x18002234c`
- `0x1800234ac`
- `0x180023b5c`

## import_xrefs

- `tbs!Tbsi_GetDeviceInfo` at `0x1800234d1`
- `tbs!Tbsi_GetDeviceInfo` at `0x1800234d1`

## string_xrefs

- `0x1800234dc`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18002351b`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18002353e`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

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
0x1800234ac  sub     rsp, 58h
0x1800234b0  mov     rax, cs:__security_cookie
0x1800234b7  xor     rax, rsp
0x1800234ba  mov     [rsp+58h+var_18], rax
0x1800234bf  xorps   xmm0, xmm0
0x1800234c2  lea     rdx, [rsp+58h+var_28]
0x1800234c7  mov     ecx, 10h
0x1800234cc  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x1800234d1  call    cs:__imp_Tbsi_GetDeviceInfo
0x1800234d7  mov     rcx, [rsp+58h]; this
0x1800234dc  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800234e3  mov     r9d, eax; char *
0x1800234e6  mov     dword ptr [rsp+58h+var_30], 8028400Fh; char *
0x1800234ee  mov     edx, 8Eh; void *
0x1800234f3  mov     [rsp+58h+var_38], 1; int
0x1800234fb  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180023500  test    eax, eax
0x180023502  jns     short loc_180023530
0x180023504  mov     rcx, [rsp+58h]; this
0x180023509  lea     rax, aTpmNotFoundInT; "TPM not found in the device"
0x180023510  mov     r9d, 80090029h; char *
0x180023516  mov     qword ptr [rsp+58h+var_38], rax; int
0x18002351b  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180023522  mov     edx, 90h; void *
0x180023527  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002352c  xor     al, al
0x18002352e  jmp     short loc_180023569
0x180023530  mov     eax, dword ptr [rsp+58h+var_28+4]
0x180023534  cmp     eax, 2
0x180023537  jnb     short loc_180023567
0x180023539  mov     rcx, [rsp+58h]; this
0x18002353e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180023545  mov     dword ptr [rsp+58h+var_30], eax; char *
0x180023549  mov     r9d, 80090029h; char *
0x18002354f  lea     rax, aTpmVersionDIsN; "TPM version %d is not supported for Ngc"...
0x180023556  mov     edx, 96h; void *
0x18002355b  mov     qword ptr [rsp+58h+var_38], rax; int
0x180023560  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023565  jmp     short loc_18002352C
0x180023567  mov     al, 1
0x180023569  mov     rcx, [rsp+58h+var_18]
0x18002356e  xor     rcx, rsp; StackCookie
0x180023571  call    __security_check_cookie
0x180023576  add     rsp, 58h
0x18002357a  retn
```
