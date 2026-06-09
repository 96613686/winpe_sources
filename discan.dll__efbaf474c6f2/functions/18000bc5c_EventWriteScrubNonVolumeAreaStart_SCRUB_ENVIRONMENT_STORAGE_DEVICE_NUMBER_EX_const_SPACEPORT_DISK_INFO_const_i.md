# EventWriteScrubNonVolumeAreaStart(_SCRUB_ENVIRONMENT *,_STORAGE_DEVICE_NUMBER_EX const *,SPACEPORT_DISK_INFO const *,__int64,unsigned __int64)

- ea: `0x18000bc5c`
- end: `0x18000be05`
- name: `?EventWriteScrubNonVolumeAreaStart@@YAXPEAU_SCRUB_ENVIRONMENT@@PEBU_STORAGE_DEVICE_NUMBER_EX@@PEBUSPACEPORT_DISK_INFO@@_J_K@Z`
- size: `425`
- prototype: `void __fastcall(struct _SCRUB_ENVIRONMENT *, const struct _STORAGE_DEVICE_NUMBER_EX *, const struct SPACEPORT_DISK_INFO *, __int64, const struct SPACEPORT_DISK_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001d80c`

## callees

- `0x1800010f4`
- `0x18000166c`
- `0x18000bc5c`
- `0x18000f6b0`
- `0x180011508`
- `0x180037620`

## pseudocode

```c
void __fastcall EventWriteScrubNonVolumeAreaStart(
        struct _SCRUB_ENVIRONMENT *a1,
        const struct _STORAGE_DEVICE_NUMBER_EX *a2,
        const struct SPACEPORT_DISK_INFO *a3,
        __int64 a4,
        const struct SPACEPORT_DISK_INFO *a5)
{
  GUID *p_DeviceGuid; // r14
  int Data3; // edi
  int v9; // ecx
  int v10; // r9d
  int v11; // r10d
  int v12; // r11d
  int v13; // ebx
  int Data2; // esi
  int v15; // r8d
  __int64 DeviceNumber; // r8
  __int64 Data1; // r9
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+30h] [rbp-D0h]
  int v27; // [rsp+38h] [rbp-C8h]
  int v28; // [rsp+40h] [rbp-C0h]
  int v29; // [rsp+48h] [rbp-B8h]
  int v30; // [rsp+50h] [rbp-B0h]
  int v31; // [rsp+58h] [rbp-A8h]
  int v32; // [rsp+60h] [rbp-A0h]
  int v33; // [rsp+68h] [rbp-98h]
  struct _UNICODE_STRING v35; // [rsp+80h] [rbp-80h] BYREF
  const struct SPACEPORT_DISK_INFO *v36; // [rsp+90h] [rbp-70h] BYREF
  struct _SCRUB_ENVIRONMENT *v37; // [rsp+98h] [rbp-68h] BYREF
  __int64 v38; // [rsp+A0h] [rbp-60h] BYREF
  char v39; // [rsp+B0h] [rbp-50h] BYREF

  p_DeviceGuid = &a2->DeviceGuid;
  Data3 = a2->DeviceGuid.Data3;
  v37 = a1;
  v9 = a2->DeviceGuid.Data4[6];
  v10 = a2->DeviceGuid.Data4[3];
  v11 = a2->DeviceGuid.Data4[2];
  v12 = a2->DeviceGuid.Data4[1];
  v13 = a2->DeviceGuid.Data4[0];
  Data2 = a2->DeviceGuid.Data2;
  v36 = a3;
  v15 = a2->DeviceGuid.Data4[4];
  v35.Buffer = (PWSTR)&v39;
  v33 = a2->DeviceGuid.Data4[7];
  v32 = v9;
  v31 = a2->DeviceGuid.Data4[5];
  v30 = v15;
  DeviceNumber = a2->DeviceNumber;
  v29 = v10;
  Data1 = a2->DeviceGuid.Data1;
  v28 = v11;
  v27 = v12;
  v26 = v13;
  v25 = Data3;
  v24 = Data2;
  *(_QWORD *)&v35.Length = 15728640;
  RtlUnicodeStringPrintf(
    &v35,
    L"\\\\?\\PhysicalDrive%u \\\\?\\Disk{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x} Offset %#I64x Length %#I64x",
    DeviceNumber,
    Data1,
    v24,
    v25,
    v26,
    v27,
    v28,
    v29,
    v30,
    v31,
    v32,
    v33,
    a4,
    a5);
  if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
    McTemplateU0hzr0hzr2qiijjjj_EventWriteTransfer(
      0,
      (_DWORD)v36,
      v35.Length >> 1,
      v35.Buffer,
      0,
      0,
      a2->DeviceNumber,
      a4,
      (char)a5,
      (__int64)p_DeviceGuid,
      (__int64)p_DeviceGuid,
      (__int64)v36,
      (__int64)v36 + 16);
  if ( (unsigned int)dword_1800470B8 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(v19, v18, v20) )
    {
      v37 = (struct _SCRUB_ENVIRONMENT *)((char *)v37 + 52);
      v36 = a5;
      v38 = a4;
      *(_QWORD *)&v35.Length = p_DeviceGuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v21,
        (__int64)word_18004097A,
        v22,
        v23,
        (__int64 *)&v37,
        (__int64 *)&v35,
        (__int64)&v38,
        (__int64)&v36);
    }
  }
}

```

## disassembly

```asm
0x18000bc5c  mov     [rsp-8+arg_0], rbx
0x18000bc61  push    rbp
0x18000bc62  push    rsi
0x18000bc63  push    rdi
0x18000bc64  push    r12
0x18000bc66  push    r13
0x18000bc68  push    r14
0x18000bc6a  push    r15
0x18000bc6c  lea     rbp, [rsp-0B0h]
0x18000bc74  sub     rsp, 1B0h
0x18000bc7b  mov     rax, cs:__security_cookie
0x18000bc82  xor     rax, rsp
0x18000bc85  mov     [rbp+0E0h+var_40], rax
0x18000bc8c  mov     r13, [rbp+0E0h+arg_20]
0x18000bc93  lea     r14, [rdx+14h]
0x18000bc97  movzx   edi, word ptr [r14+6]
0x18000bc9c  lea     rax, [rbp+0E0h+var_130]
0x18000bca0  mov     [rsp+1E0h+var_168], r13
0x18000bca5  mov     r15, rdx
0x18000bca8  mov     r12, r9
0x18000bcab  mov     [rbp+0E0h+var_148], rcx
0x18000bcaf  movzx   ecx, byte ptr [rdx+22h]
0x18000bcb3  mov     [rsp+1E0h+var_170], r12
0x18000bcb8  movzx   r9d, byte ptr [r15+1Fh]
0x18000bcbd  movzx   r10d, byte ptr [r15+1Eh]
0x18000bcc2  movzx   r11d, byte ptr [r15+1Dh]
0x18000bcc7  movzx   ebx, byte ptr [r15+1Ch]
0x18000bccc  movzx   esi, word ptr [r15+18h]
0x18000bcd1  mov     [rbp+0E0h+var_150], r8
0x18000bcd5  movzx   r8d, byte ptr [r15+20h]
0x18000bcda  mov     [rbp+0E0h+var_160.Buffer], rax
0x18000bcde  movzx   eax, byte ptr [rdx+23h]
0x18000bce2  movzx   edx, byte ptr [rdx+21h]
0x18000bce6  mov     [rsp+1E0h+var_178], eax
0x18000bcea  mov     dword ptr [rsp+1E0h+var_180], ecx
0x18000bcee  lea     rcx, [rbp+0E0h+var_160]; struct _UNICODE_STRING *
0x18000bcf2  mov     dword ptr [rsp+1E0h+var_188], edx
0x18000bcf6  lea     rdx, aPhysicaldriveU_0; "\\\\?\\PhysicalDrive%u \\\\?\\Disk{%08x"...
0x18000bcfd  mov     dword ptr [rsp+1E0h+var_190], r8d
0x18000bd02  mov     r8d, [r15+10h]
0x18000bd06  mov     dword ptr [rsp+1E0h+var_198], r9d
0x18000bd0b  mov     r9d, [r14]
0x18000bd0e  mov     dword ptr [rsp+1E0h+var_1A0], r10d
0x18000bd13  mov     dword ptr [rsp+1E0h+var_1A8], r11d
0x18000bd18  mov     dword ptr [rsp+1E0h+var_1B0], ebx
0x18000bd1c  mov     dword ptr [rsp+1E0h+var_1B8], edi
0x18000bd20  mov     dword ptr [rsp+1E0h+var_1C0], esi
0x18000bd24  mov     qword ptr [rbp+0E0h+var_160.Length], 0F00000h
0x18000bd2c  call    ?RtlUnicodeStringPrintf@@YAJPEAU_UNICODE_STRING@@PEBGZZ; RtlUnicodeStringPrintf(_UNICODE_STRING *,ushort const *,...)
0x18000bd31  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 8
0x18000bd38  jz      short loc_18000BD86
0x18000bd3a  mov     rdx, [rbp+0E0h+var_150]
0x18000bd3e  xor     ecx, ecx
0x18000bd40  movzx   r8d, [rbp+0E0h+var_160.Length]
0x18000bd45  mov     r9, [rbp+0E0h+var_160.Buffer]
0x18000bd49  shr     r8w, 1
0x18000bd4d  lea     rax, [rdx+10h]
0x18000bd51  mov     [rsp+1E0h+var_180], rax
0x18000bd56  mov     eax, [r15+10h]
0x18000bd5a  mov     [rsp+1E0h+var_188], rdx
0x18000bd5f  mov     [rsp+1E0h+var_190], r14
0x18000bd64  mov     [rsp+1E0h+var_198], r14
0x18000bd69  mov     [rsp+1E0h+var_1A0], r13
0x18000bd6e  mov     [rsp+1E0h+var_1A8], r12
0x18000bd73  mov     dword ptr [rsp+1E0h+var_1B0], eax
0x18000bd77  mov     [rsp+1E0h+var_1B8], rcx
0x18000bd7c  mov     word ptr [rsp+1E0h+var_1C0], cx
0x18000bd81  call    McTemplateU0hzr0hzr2qiijjjj_EventWriteTransfer
0x18000bd86  mov     eax, cs:dword_1800470B8
0x18000bd8c  cmp     eax, 5
0x18000bd8f  jbe     short loc_18000BDDB
0x18000bd91  call    _tlgKeywordOn
0x18000bd96  test    al, al
0x18000bd98  jz      short loc_18000BDDB
0x18000bd9a  add     [rbp+0E0h+var_148], 34h ; '4'
0x18000bd9f  lea     rax, [rbp+0E0h+var_150]
0x18000bda3  mov     [rsp+1E0h+var_1A8], rax
0x18000bda8  lea     rdx, word_18004097A
0x18000bdaf  lea     rax, [rbp+0E0h+var_140]
0x18000bdb3  mov     [rbp+0E0h+var_150], r13
0x18000bdb7  mov     [rsp+1E0h+var_1B0], rax
0x18000bdbc  lea     rax, [rbp+0E0h+var_160]
0x18000bdc0  mov     [rsp+1E0h+var_1B8], rax
0x18000bdc5  lea     rax, [rbp+0E0h+var_148]
0x18000bdc9  mov     [rsp+1E0h+var_1C0], rax
0x18000bdce  mov     [rbp+0E0h+var_140], r12
0x18000bdd2  mov     qword ptr [rbp+0E0h+var_160.Length], r14
0x18000bdd6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000bddb  mov     rcx, [rbp+0E0h+var_40]
0x18000bde2  xor     rcx, rsp; StackCookie
0x18000bde5  call    __security_check_cookie
0x18000bdea  mov     rbx, [rsp+1E0h+arg_0]
0x18000bdf2  add     rsp, 1B0h
0x18000bdf9  pop     r15
0x18000bdfb  pop     r14
0x18000bdfd  pop     r13
0x18000bdff  pop     r12
0x18000be01  pop     rdi
0x18000be02  pop     rsi
0x18000be03  pop     rbp
0x18000be04  retn
```
