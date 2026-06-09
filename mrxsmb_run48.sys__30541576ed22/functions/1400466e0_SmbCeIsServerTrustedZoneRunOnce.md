# SmbCeIsServerTrustedZoneRunOnce

- ea: `0x1400466e0`
- end: `0x1400468c2`
- name: `SmbCeIsServerTrustedZoneRunOnce`
- size: `482`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14003838c`
- `0x1400383d0`
- `0x14003a0bc`
- `0x1400400c4`
- `0x1400466e0`
- `0x14008a85c`

## import_xrefs

- `ntoskrnl!RtlValidSid` at `0x14004670e`
- `ntoskrnl!RtlValidSid` at `0x14004670e`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14004677b`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14004677b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004680c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004680c`

## pseudocode

```c
__int64 __fastcall SmbCeIsServerTrustedZoneRunOnce(PRTL_RUN_ONCE a1, _QWORD *a2, PVOID *a3)
{
  char *v3; // rdi
  NTSTATUS v5; // eax
  __int64 v6; // r9
  int v7; // ebp
  UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v10; // [rsp+68h] [rbp+10h] BYREF

  v3 = (char *)a2 + 484;
  v10 = 3;
  UnicodeString = 0;
  if ( !RtlValidSid((char *)a2 + 484) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 39, &WPP_84a53c2c5f823219b45553a65390e18c_Traceguids, a2);
    }
    return 0;
  }
  v5 = RtlConvertSidToUnicodeString(&UnicodeString, v3, 1u);
  v6 = (unsigned int)v5;
  if ( v5 < 0 || !UnicodeString.Length )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_dq(
        WPP_GLOBAL_Control->AttachedDevice,
        40,
        &WPP_84a53c2c5f823219b45553a65390e18c_Traceguids,
        (unsigned int)v5,
        a2);
    }
    return 0;
  }
  if ( UnicodeString.Length > 0x176u )
    __int2c();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Zq(
      WPP_GLOBAL_Control->AttachedDevice,
      41,
      (unsigned int)&WPP_84a53c2c5f823219b45553a65390e18c_Traceguids,
      (unsigned int)&UnicodeString,
      (char)a2);
  }
  v7 = SmbMapUrlToZone(a2[48] + 128LL, &UnicodeString, &v10, v6);
  RtlFreeUnicodeString(&UnicodeString);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        42,
        &WPP_84a53c2c5f823219b45553a65390e18c_Traceguids,
        (unsigned int)v7);
    }
    return 0;
  }
  if ( *((_BYTE *)a2 + 480) )
    __int2c();
  *((_BYTE *)a2 + 480) = v10 < 3;
  return 1;
}

```

## disassembly

```asm
0x1400466e0  mov     rax, rsp
0x1400466e3  mov     [rax+8], rbx
0x1400466e7  mov     [rax+18h], rbp
0x1400466eb  push    rsi
0x1400466ec  push    rdi
0x1400466ed  push    r14
0x1400466ef  sub     rsp, 40h
0x1400466f3  lea     rdi, [rdx+1E4h]
0x1400466fa  mov     dword ptr [rax+10h], 3
0x140046701  xorps   xmm0, xmm0
0x140046704  mov     rcx, rdi; Sid
0x140046707  mov     rsi, rdx
0x14004670a  movups  xmmword ptr [rax-28h], xmm0
0x14004670e  call    cs:__imp_RtlValidSid
0x140046715  nop     dword ptr [rax+rax+00h]
0x14004671a  xor     r14d, r14d
0x14004671d  test    al, al
0x14004671f  jnz     short loc_14004676B
0x140046721  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140046728  lea     rdi, WPP_GLOBAL_Control
0x14004672f  cmp     rcx, rdi
0x140046732  jz      loc_1400468AC
0x140046738  mov     eax, [rcx+2Ch]
0x14004673b  lea     ebx, [r14+1]
0x14004673f  test    bl, al
0x140046741  jz      loc_1400468AC
0x140046747  cmp     [rcx+29h], bl
0x14004674a  jb      loc_1400468AC
0x140046750  mov     rcx, [rcx+18h]
0x140046754  lea     edx, [rbx+26h]
0x140046757  mov     r9, rsi
0x14004675a  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x140046761  call    WPP_SF_q
0x140046766  jmp     loc_1400468AC
0x14004676b  mov     ebx, 1
0x140046770  lea     rcx, [rsp+58h+UnicodeString]; UnicodeString
0x140046775  mov     r8b, bl; AllocateDestinationString
0x140046778  mov     rdx, rdi; Sid
0x14004677b  call    cs:__imp_RtlConvertSidToUnicodeString
0x140046782  nop     dword ptr [rax+rax+00h]
0x140046787  mov     r9d, eax
0x14004678a  test    eax, eax
0x14004678c  js      loc_140046873
0x140046792  movzx   ecx, [rsp+58h+UnicodeString.Length]
0x140046797  test    cx, cx
0x14004679a  jz      loc_140046873
0x1400467a0  mov     eax, 176h
0x1400467a5  cmp     cx, ax
0x1400467a8  jbe     short loc_1400467AC
0x1400467aa  int     2Ch; Windows NT - assertion failure
0x1400467ac  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400467b3  lea     rdi, WPP_GLOBAL_Control
0x1400467ba  cmp     rcx, rdi
0x1400467bd  jz      short loc_1400467EB
0x1400467bf  mov     eax, [rcx+2Ch]
0x1400467c2  test    al, 8
0x1400467c4  jz      short loc_1400467EB
0x1400467c6  cmp     byte ptr [rcx+29h], 2
0x1400467ca  jb      short loc_1400467EB
0x1400467cc  mov     rcx, [rcx+18h]
0x1400467d0  lea     r9, [rsp+58h+UnicodeString]
0x1400467d5  mov     edx, 29h ; ')'
0x1400467da  mov     [rsp+58h+var_38], rsi
0x1400467df  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x1400467e6  call    WPP_SF_Zq
0x1400467eb  mov     rcx, [rsi+180h]
0x1400467f2  lea     r8, [rsp+58h+arg_8]
0x1400467f7  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1400467fb  lea     rdx, [rsp+58h+UnicodeString]
0x140046800  call    SmbMapUrlToZone
0x140046805  lea     rcx, [rsp+58h+UnicodeString]; UnicodeString
0x14004680a  mov     ebp, eax
0x14004680c  call    cs:__imp_RtlFreeUnicodeString
0x140046813  nop     dword ptr [rax+rax+00h]
0x140046818  test    ebp, ebp
0x14004681a  jns     short loc_140046852
0x14004681c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140046823  cmp     rcx, rdi
0x140046826  jz      loc_1400468AC
0x14004682c  mov     edx, [rcx+2Ch]
0x14004682f  test    bl, dl
0x140046831  jz      short loc_1400468AC
0x140046833  cmp     [rcx+29h], bl
0x140046836  jb      short loc_1400468AC
0x140046838  mov     rcx, [rcx+18h]
0x14004683c  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x140046843  mov     edx, 2Ah ; '*'
0x140046848  mov     r9d, ebp
0x14004684b  call    WPP_SF_d
0x140046850  jmp     short loc_1400468AC
0x140046852  cmp     [rsp+58h+arg_8], 3
0x140046857  movzx   eax, r14b
0x14004685b  cmovb   eax, ebx
0x14004685e  cmp     [rsi+1E0h], r14b
0x140046865  jz      short loc_140046869
0x140046867  int     2Ch; Windows NT - assertion failure
0x140046869  mov     [rsi+1E0h], al
0x14004686f  mov     eax, ebx
0x140046871  jmp     short loc_1400468AE
0x140046873  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004687a  lea     rdi, WPP_GLOBAL_Control
0x140046881  cmp     rcx, rdi
0x140046884  jz      short loc_1400468AC
0x140046886  mov     eax, [rcx+2Ch]
0x140046889  test    bl, al
0x14004688b  jz      short loc_1400468AC
0x14004688d  cmp     [rcx+29h], bl
0x140046890  jb      short loc_1400468AC
0x140046892  mov     rcx, [rcx+18h]
0x140046896  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x14004689d  mov     edx, 28h ; '('
0x1400468a2  mov     [rsp+58h+var_38], rsi
0x1400468a7  call    WPP_SF_dq
0x1400468ac  xor     eax, eax
0x1400468ae  mov     rbx, [rsp+58h+arg_0]
0x1400468b3  mov     rbp, [rsp+58h+arg_10]
0x1400468b8  add     rsp, 40h
0x1400468bc  pop     r14
0x1400468be  pop     rdi
0x1400468bf  pop     rsi
0x1400468c0  retn
```
