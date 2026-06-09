# NgcUtils::DoesTPMSupportNgcIso(void)

- ea: `0x18001be14`
- end: `0x18001bee3`
- name: `?DoesTPMSupportNgcIso@NgcUtils@@YA_NXZ`
- size: `207`
- prototype: `char __fastcall(NgcUtils *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001bdbc`

## callees

- `0x180006330`
- `0x18001be14`
- `0x18001c520`
- `0x18001c564`

## import_xrefs

- `tbs!Tbsi_GetDeviceInfo` at `0x18001be39`
- `tbs!Tbsi_GetDeviceInfo` at `0x18001be39`

## string_xrefs

- `0x18001be44`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18001be83`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18001bea6`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

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
0x18001be14  sub     rsp, 58h
0x18001be18  mov     rax, cs:__security_cookie
0x18001be1f  xor     rax, rsp
0x18001be22  mov     [rsp+58h+var_18], rax
0x18001be27  xorps   xmm0, xmm0
0x18001be2a  lea     rdx, [rsp+58h+var_28]
0x18001be2f  mov     ecx, 10h
0x18001be34  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x18001be39  call    cs:__imp_Tbsi_GetDeviceInfo
0x18001be3f  mov     rcx, [rsp+58h]; this
0x18001be44  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001be4b  mov     r9d, eax; char *
0x18001be4e  mov     dword ptr [rsp+58h+var_30], 8028400Fh; char *
0x18001be56  mov     edx, 8Eh; void *
0x18001be5b  mov     [rsp+58h+var_38], 1; int
0x18001be63  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x18001be68  test    eax, eax
0x18001be6a  jns     short loc_18001BE98
0x18001be6c  mov     rcx, [rsp+58h]; this
0x18001be71  lea     rax, aTpmNotFoundInT; "TPM not found in the device"
0x18001be78  mov     r9d, 80090029h; char *
0x18001be7e  mov     qword ptr [rsp+58h+var_38], rax; int
0x18001be83  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001be8a  mov     edx, 90h; void *
0x18001be8f  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001be94  xor     al, al
0x18001be96  jmp     short loc_18001BED1
0x18001be98  mov     eax, dword ptr [rsp+58h+var_28+4]
0x18001be9c  cmp     eax, 2
0x18001be9f  jnb     short loc_18001BECF
0x18001bea1  mov     rcx, [rsp+58h]; this
0x18001bea6  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001bead  mov     dword ptr [rsp+58h+var_30], eax; char *
0x18001beb1  mov     r9d, 80090029h; char *
0x18001beb7  lea     rax, aTpmVersionDIsN; "TPM version %d is not supported for Ngc"...
0x18001bebe  mov     edx, 96h; void *
0x18001bec3  mov     qword ptr [rsp+58h+var_38], rax; int
0x18001bec8  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001becd  jmp     short loc_18001BE94
0x18001becf  mov     al, 1
0x18001bed1  mov     rcx, [rsp+58h+var_18]
0x18001bed6  xor     rcx, rsp; StackCookie
0x18001bed9  call    __security_check_cookie
0x18001bede  add     rsp, 58h
0x18001bee2  retn
```
