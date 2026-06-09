# EventWriteScrubNonVolumeAreaComplete(_SCRUB_ENVIRONMENT *,_STORAGE_DEVICE_NUMBER_EX const *,__int64,unsigned __int64,long,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x18000b9a8`
- end: `0x18000bc53`
- name: `?EventWriteScrubNonVolumeAreaComplete@@YAXPEAU_SCRUB_ENVIRONMENT@@PEBU_STORAGE_DEVICE_NUMBER_EX@@_J_KJ333@Z`
- size: `683`
- prototype: `void __fastcall(struct _SCRUB_ENVIRONMENT *, const struct _STORAGE_DEVICE_NUMBER_EX *, __int64, __int64, int, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001d80c`

## callees

- `0x180001428`
- `0x18000166c`
- `0x18000b9a8`
- `0x18000f6b0`
- `0x180010ea8`
- `0x180037620`

## pseudocode

```c
void __fastcall EventWriteScrubNonVolumeAreaComplete(
        struct _SCRUB_ENVIRONMENT *a1,
        const struct _STORAGE_DEVICE_NUMBER_EX *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 a7,
        unsigned __int64 a8)
{
  int v9; // ecx
  GUID *p_DeviceGuid; // r15
  int Data3; // edi
  __int64 DeviceNumber; // r8
  __int64 Data1; // r9
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 *v19; // rdx
  DWORD v20; // eax
  unsigned __int64 v21; // r14
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  int Data2; // [rsp+20h] [rbp-160h]
  int v26; // [rsp+28h] [rbp-158h]
  int v27; // [rsp+30h] [rbp-150h]
  int v28; // [rsp+38h] [rbp-148h]
  int v29; // [rsp+40h] [rbp-140h]
  int v30; // [rsp+48h] [rbp-138h]
  int v31; // [rsp+50h] [rbp-130h]
  int v32; // [rsp+58h] [rbp-128h]
  int v33; // [rsp+60h] [rbp-120h]
  int v34; // [rsp+68h] [rbp-118h]
  struct _UNICODE_STRING v37; // [rsp+100h] [rbp-80h] BYREF
  int v38; // [rsp+110h] [rbp-70h] BYREF
  struct _SCRUB_ENVIRONMENT *v39; // [rsp+118h] [rbp-68h] BYREF
  __int64 v40; // [rsp+120h] [rbp-60h] BYREF
  __int64 v41; // [rsp+128h] [rbp-58h] BYREF
  unsigned __int64 v42; // [rsp+130h] [rbp-50h] BYREF
  unsigned __int64 v43; // [rsp+138h] [rbp-48h] BYREF
  unsigned __int64 v44; // [rsp+140h] [rbp-40h] BYREF
  char v45; // [rsp+150h] [rbp-30h] BYREF

  v39 = a1;
  v9 = a2->DeviceGuid.Data4[6];
  p_DeviceGuid = &a2->DeviceGuid;
  Data3 = a2->DeviceGuid.Data3;
  v37.Buffer = (PWSTR)&v45;
  v34 = a2->DeviceGuid.Data4[7];
  v33 = v9;
  v32 = a2->DeviceGuid.Data4[5];
  v31 = a2->DeviceGuid.Data4[4];
  DeviceNumber = a2->DeviceNumber;
  v30 = a2->DeviceGuid.Data4[3];
  Data1 = a2->DeviceGuid.Data1;
  v29 = a2->DeviceGuid.Data4[2];
  v28 = a2->DeviceGuid.Data4[1];
  v27 = a2->DeviceGuid.Data4[0];
  v26 = Data3;
  Data2 = a2->DeviceGuid.Data2;
  *(_QWORD *)&v37.Length = 15728640;
  RtlUnicodeStringPrintf(
    &v37,
    L"\\\\?\\PhysicalDrive%u \\\\?\\Disk{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x} Offset %#I64x Length %#I64x",
    DeviceNumber,
    Data1,
    Data2,
    v26,
    v27,
    v28,
    v29,
    v30,
    v31,
    v32,
    v33,
    v34,
    a3,
    a4);
  if ( a5 < 0 )
  {
    if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 0x10) != 0 )
    {
      v19 = DISCANCR_EVENT_VOLUME_SCAN_COMPLETE_WITH_ERROR;
      goto LABEL_4;
    }
  }
  else if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
  {
    v19 = DISCANCR_EVENT_VOLUME_SCAN_COMPLETE;
LABEL_4:
    v20 = a2->DeviceNumber;
    v21 = a6;
    McTemplateU0hzr0hzr2dxxxxxiiiiiiiiiiiiiiqxqiij_EventWriteTransfer(
      v17,
      (_DWORD)v19,
      v37.Length >> 1,
      v37.Buffer,
      0,
      0,
      a5,
      0,
      0,
      0,
      0,
      0,
      a6,
      a7,
      0,
      0,
      0,
      0,
      0,
      0,
      0,
      0,
      0,
      0,
      0,
      0,
      1,
      a8,
      v20,
      a3,
      a4,
      (__int64)p_DeviceGuid);
    goto LABEL_8;
  }
  v21 = a6;
LABEL_8:
  if ( (unsigned int)dword_1800470B8 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(v17, v16, v18) )
    {
      v39 = (struct _SCRUB_ENVIRONMENT *)((char *)v39 + 52);
      v40 = a4;
      v41 = a3;
      v42 = a8;
      v38 = a5;
      v43 = a7;
      v44 = v21;
      *(_QWORD *)&v37.Length = p_DeviceGuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v22,
        (__int64)byte_1800408D5,
        v23,
        v24,
        (__int64 *)&v39,
        (__int64 *)&v37,
        (__int64)&v44,
        (__int64)&v43,
        (__int64)&v38,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v40);
    }
  }
}

```

## disassembly

```asm
0x18000b9a8  mov     [rsp-8+arg_0], rbx
0x18000b9ad  push    rbp
0x18000b9ae  push    rsi
0x18000b9af  push    rdi
0x18000b9b0  push    r12
0x18000b9b2  push    r13
0x18000b9b4  push    r14
0x18000b9b6  push    r15
0x18000b9b8  lea     rbp, [rsp-0D0h]
0x18000b9c0  sub     rsp, 250h
0x18000b9c7  mov     rax, cs:__security_cookie
0x18000b9ce  xor     rax, rsp
0x18000b9d1  mov     [rbp+100h+var_40], rax
0x18000b9d8  mov     r14, rdx
0x18000b9db  mov     [rbp+100h+var_168], rcx
0x18000b9df  movzx   ecx, byte ptr [rdx+22h]
0x18000b9e3  lea     r15, [rdx+14h]
0x18000b9e7  movzx   edi, word ptr [r15+6]
0x18000b9ec  lea     rax, [rbp+100h+var_130]
0x18000b9f0  mov     r13, r9
0x18000b9f3  mov     [rbp+100h+var_180.Buffer], rax
0x18000b9f7  movzx   eax, byte ptr [rdx+23h]
0x18000b9fb  mov     r12, r8
0x18000b9fe  movzx   edx, byte ptr [rdx+21h]
0x18000ba02  movzx   r8d, byte ptr [r14+20h]
0x18000ba07  movzx   r9d, byte ptr [r14+1Fh]
0x18000ba0c  movzx   r10d, byte ptr [r14+1Eh]
0x18000ba11  movzx   r11d, byte ptr [r14+1Dh]
0x18000ba16  movzx   ebx, byte ptr [r14+1Ch]
0x18000ba1b  movzx   esi, word ptr [r14+18h]
0x18000ba20  mov     [rsp+280h+var_208], r13
0x18000ba25  mov     [rsp+280h+var_210], r12
0x18000ba2a  mov     dword ptr [rsp+280h+var_218], eax
0x18000ba2e  mov     dword ptr [rsp+280h+var_220], ecx
0x18000ba32  lea     rcx, [rbp+100h+var_180]; struct _UNICODE_STRING *
0x18000ba36  mov     dword ptr [rsp+280h+var_228], edx
0x18000ba3a  lea     rdx, aPhysicaldriveU_0; "\\\\?\\PhysicalDrive%u \\\\?\\Disk{%08x"...
0x18000ba41  mov     dword ptr [rsp+280h+var_230], r8d
0x18000ba46  mov     r8d, [r14+10h]
0x18000ba4a  mov     dword ptr [rsp+280h+var_238], r9d
0x18000ba4f  mov     r9d, [r15]
0x18000ba52  mov     dword ptr [rsp+280h+var_240], r10d
0x18000ba57  mov     dword ptr [rsp+280h+var_248], r11d
0x18000ba5c  mov     dword ptr [rsp+280h+var_250], ebx
0x18000ba60  mov     dword ptr [rsp+280h+var_258], edi
0x18000ba64  mov     dword ptr [rsp+280h+var_260], esi
0x18000ba68  mov     qword ptr [rbp+100h+var_180.Length], 0F00000h
0x18000ba70  call    ?RtlUnicodeStringPrintf@@YAJPEAU_UNICODE_STRING@@PEBGZZ; RtlUnicodeStringPrintf(_UNICODE_STRING *,ushort const *,...)
0x18000ba75  mov     ebx, [rbp+100h+arg_20]
0x18000ba7b  xor     r9d, r9d
0x18000ba7e  mov     rdi, [rbp+100h+arg_38]
0x18000ba85  mov     rsi, [rbp+100h+arg_30]
0x18000ba8c  test    ebx, ebx
0x18000ba8e  js      loc_18000BB85
0x18000ba94  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 8
0x18000ba9b  jz      loc_18000BB9A
0x18000baa1  lea     rdx, DISCANCR_EVENT_VOLUME_SCAN_COMPLETE
0x18000baa8  mov     eax, [r14+10h]
0x18000baac  movzx   r8d, [rbp+100h+var_180.Length]
0x18000bab1  mov     r14, [rbp+100h+arg_28]
0x18000bab8  mov     [rsp+280h+var_188], r15
0x18000bac0  mov     [rsp+280h+var_190], r13
0x18000bac8  mov     [rsp+280h+var_198], r12
0x18000bad0  mov     [rsp+280h+var_1A0], eax
0x18000bad7  mov     [rsp+280h+var_1A8], rdi
0x18000badf  mov     [rsp+280h+var_1B0], 1
0x18000baea  mov     [rsp+280h+var_1B8], r9
0x18000baf2  mov     [rsp+280h+var_1C0], r9
0x18000bafa  mov     [rsp+280h+var_1C8], r9
0x18000bb02  mov     [rsp+280h+var_1D0], r9
0x18000bb0a  mov     [rsp+280h+var_1D8], r9
0x18000bb12  mov     [rsp+280h+var_1E0], r9
0x18000bb1a  mov     [rsp+280h+var_1E8], r9
0x18000bb22  mov     [rsp+280h+var_1F0], r9
0x18000bb2a  mov     [rsp+280h+var_1F8], r9
0x18000bb32  mov     [rsp+280h+var_200], r9
0x18000bb3a  mov     [rsp+280h+var_208], r9
0x18000bb3f  mov     [rsp+280h+var_210], r9
0x18000bb44  mov     [rsp+280h+var_218], rsi
0x18000bb49  mov     [rsp+280h+var_220], r14
0x18000bb4e  mov     [rsp+280h+var_228], r9
0x18000bb53  mov     [rsp+280h+var_230], r9
0x18000bb58  mov     [rsp+280h+var_238], r9
0x18000bb5d  mov     [rsp+280h+var_240], r9
0x18000bb62  mov     [rsp+280h+var_248], r9
0x18000bb67  mov     dword ptr [rsp+280h+var_250], ebx
0x18000bb6b  mov     [rsp+280h+var_258], r9
0x18000bb70  mov     word ptr [rsp+280h+var_260], r9w
0x18000bb76  mov     r9, [rbp+100h+var_180.Buffer]
0x18000bb7a  shr     r8w, 1
0x18000bb7e  call    McTemplateU0hzr0hzr2dxxxxxiiiiiiiiiiiiiiqxqiij_EventWriteTransfer
0x18000bb83  jmp     short loc_18000BBA1
0x18000bb85  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 10h
0x18000bb8c  jz      short loc_18000BB9A
0x18000bb8e  lea     rdx, DISCANCR_EVENT_VOLUME_SCAN_COMPLETE_WITH_ERROR
0x18000bb95  jmp     loc_18000BAA8
0x18000bb9a  mov     r14, [rbp+100h+arg_28]
0x18000bba1  mov     eax, cs:dword_1800470B8
0x18000bba7  cmp     eax, 5
0x18000bbaa  jbe     short loc_18000BC29
0x18000bbac  call    _tlgKeywordOn
0x18000bbb1  test    al, al
0x18000bbb3  jz      short loc_18000BC29
0x18000bbb5  add     [rbp+100h+var_168], 34h ; '4'
0x18000bbba  lea     rax, [rbp+100h+var_160]
0x18000bbbe  mov     [rsp+280h+var_228], rax
0x18000bbc3  lea     rdx, byte_1800408D5
0x18000bbca  lea     rax, [rbp+100h+var_158]
0x18000bbce  mov     [rbp+100h+var_160], r13
0x18000bbd2  mov     [rsp+280h+var_230], rax
0x18000bbd7  lea     rax, [rbp+100h+var_150]
0x18000bbdb  mov     [rsp+280h+var_238], rax
0x18000bbe0  lea     rax, [rbp+100h+var_170]
0x18000bbe4  mov     [rsp+280h+var_240], rax
0x18000bbe9  lea     rax, [rbp+100h+var_148]
0x18000bbed  mov     [rsp+280h+var_248], rax
0x18000bbf2  lea     rax, [rbp+100h+var_140]
0x18000bbf6  mov     [rsp+280h+var_250], rax
0x18000bbfb  lea     rax, [rbp+100h+var_180]
0x18000bbff  mov     [rsp+280h+var_258], rax
0x18000bc04  lea     rax, [rbp+100h+var_168]
0x18000bc08  mov     [rsp+280h+var_260], rax
0x18000bc0d  mov     [rbp+100h+var_158], r12
0x18000bc11  mov     [rbp+100h+var_150], rdi
0x18000bc15  mov     [rbp+100h+var_170], ebx
0x18000bc18  mov     [rbp+100h+var_148], rsi
0x18000bc1c  mov     [rbp+100h+var_140], r14
0x18000bc20  mov     qword ptr [rbp+100h+var_180.Length], r15
0x18000bc24  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$07@@U2@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$07@@4AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000bc29  mov     rcx, [rbp+100h+var_40]
0x18000bc30  xor     rcx, rsp; StackCookie
0x18000bc33  call    __security_check_cookie
0x18000bc38  mov     rbx, [rsp+280h+arg_0]
0x18000bc40  add     rsp, 250h
0x18000bc47  pop     r15
0x18000bc49  pop     r14
0x18000bc4b  pop     r13
0x18000bc4d  pop     r12
0x18000bc4f  pop     rdi
0x18000bc50  pop     rsi
0x18000bc51  pop     rbp
0x18000bc52  retn
```
