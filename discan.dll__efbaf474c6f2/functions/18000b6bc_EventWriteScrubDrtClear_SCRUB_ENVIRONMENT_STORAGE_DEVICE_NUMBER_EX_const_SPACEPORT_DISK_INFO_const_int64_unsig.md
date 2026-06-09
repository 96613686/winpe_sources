# EventWriteScrubDrtClear(_SCRUB_ENVIRONMENT *,_STORAGE_DEVICE_NUMBER_EX const *,SPACEPORT_DISK_INFO const *,__int64,unsigned __int64,long,uchar)

- ea: `0x18000b6bc`
- end: `0x18000b8b1`
- name: `?EventWriteScrubDrtClear@@YAXPEAU_SCRUB_ENVIRONMENT@@PEBU_STORAGE_DEVICE_NUMBER_EX@@PEBUSPACEPORT_DISK_INFO@@_J_KJE@Z`
- size: `501`
- prototype: `void __fastcall(struct _SCRUB_ENVIRONMENT *, const struct _STORAGE_DEVICE_NUMBER_EX *, const struct SPACEPORT_DISK_INFO *, __int64, unsigned __int64, int, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009960`

## callees

- `0x18000166c`
- `0x1800016a0`
- `0x18000b6bc`
- `0x18000f6b0`
- `0x180010c7c`
- `0x180037620`

## pseudocode

```c
void __fastcall EventWriteScrubDrtClear(
        struct _SCRUB_ENVIRONMENT *a1,
        const struct _STORAGE_DEVICE_NUMBER_EX *a2,
        const struct SPACEPORT_DISK_INFO *a3,
        __int64 a4,
        unsigned __int64 a5,
        int a6,
        char a7)
{
  GUID *p_DeviceGuid; // r14
  int Data3; // edi
  __int64 DeviceNumber; // r8
  __int64 Data1; // r9
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 *v16; // rdx
  int Data2; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+40h] [rbp-C0h]
  struct _UNICODE_STRING v19; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v21; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v22[32]; // [rsp+A0h] [rbp-60h] BYREF
  GUID *v23; // [rsp+C0h] [rbp-40h]
  __int64 v24; // [rsp+C8h] [rbp-38h]
  int *v25; // [rsp+D0h] [rbp-30h]
  __int64 v26; // [rsp+D8h] [rbp-28h]
  struct _UNICODE_STRING *v27; // [rsp+E0h] [rbp-20h]
  __int64 v28; // [rsp+E8h] [rbp-18h]
  unsigned __int64 *v29; // [rsp+F0h] [rbp-10h]
  __int64 v30; // [rsp+F8h] [rbp-8h]
  char v31; // [rsp+100h] [rbp+0h] BYREF

  p_DeviceGuid = &a2->DeviceGuid;
  Data3 = a2->DeviceGuid.Data3;
  v19.Buffer = (PWSTR)&v31;
  DeviceNumber = a2->DeviceNumber;
  Data1 = a2->DeviceGuid.Data1;
  v18 = a2->DeviceGuid.Data4[2];
  Data2 = a2->DeviceGuid.Data2;
  *(_QWORD *)&v19.Length = 15728640;
  RtlUnicodeStringPrintf(
    &v19,
    L"\\\\?\\PhysicalDrive%u \\\\?\\Disk{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x} Offset %#I64x Length %#I64x",
    DeviceNumber,
    Data1);
  if ( a6 < 0 )
  {
    if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 0x10) == 0 )
      goto LABEL_8;
    v16 = DISCANCR_EVENT_VOLUME_DRT_CLEAR_WITH_ERROR;
    goto LABEL_7;
  }
  if ( a7 )
    return;
  if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
  {
    v16 = DISCANCR_EVENT_VOLUME_DRT_CLEAR;
LABEL_7:
    McTemplateU0hzr0hzr2dqiijjjj_EventWriteTransfer(
      v14,
      (_DWORD)v16,
      v19.Length >> 1,
      v19.Buffer,
      Data2,
      Data3,
      a6,
      a2->DeviceNumber,
      v18,
      a5,
      (__int64)p_DeviceGuid,
      (__int64)p_DeviceGuid,
      (__int64)a3,
      (__int64)a3 + 16);
  }
LABEL_8:
  if ( (unsigned int)dword_1800470B8 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(v14, v13, v15) )
    {
      v21 = a5;
      v29 = &v21;
      *(_QWORD *)&v19.Length = 0;
      v27 = &v19;
      v20 = a6;
      v25 = &v20;
      v30 = 8;
      v28 = 8;
      v26 = 4;
      v23 = p_DeviceGuid;
      v24 = 16;
      tlgWriteTransfer_EventWriteTransfer(&dword_1800470B8, byte_1800409DB, 0, 0, 6, v22);
    }
  }
}

```

## disassembly

```asm
0x18000b6bc  mov     [rsp-8+arg_0], rbx
0x18000b6c1  push    rbp
0x18000b6c2  push    rsi
0x18000b6c3  push    rdi
0x18000b6c4  push    r12
0x18000b6c6  push    r13
0x18000b6c8  push    r14
0x18000b6ca  push    r15
0x18000b6cc  lea     rbp, [rsp-100h]
0x18000b6d4  sub     rsp, 200h
0x18000b6db  mov     rax, cs:__security_cookie
0x18000b6e2  xor     rax, rsp
0x18000b6e5  mov     [rbp+130h+var_40], rax
0x18000b6ec  movzx   ecx, byte ptr [rdx+22h]
0x18000b6f0  lea     r14, [rdx+14h]
0x18000b6f4  movzx   edi, word ptr [r14+6]
0x18000b6f9  lea     rax, [rbp+130h+var_130]
0x18000b6fd  mov     r12, [rbp+130h+arg_20]
0x18000b704  mov     r13, rdx
0x18000b707  mov     [rsp+230h+var_1B8], r12
0x18000b70c  mov     r15, r8
0x18000b70f  mov     [rsp+230h+var_1C0], 0
0x18000b718  mov     [rbp+130h+var_1B0.Buffer], rax
0x18000b71c  movzx   eax, byte ptr [rdx+23h]
0x18000b720  movzx   edx, byte ptr [rdx+21h]
0x18000b724  movzx   r8d, byte ptr [r13+20h]
0x18000b729  movzx   r9d, byte ptr [r13+1Fh]
0x18000b72e  movzx   r10d, byte ptr [r13+1Eh]
0x18000b733  movzx   r11d, byte ptr [r13+1Dh]
0x18000b738  movzx   ebx, byte ptr [r13+1Ch]
0x18000b73d  movzx   esi, word ptr [r13+18h]
0x18000b742  mov     dword ptr [rsp+230h+var_1C8], eax
0x18000b746  mov     dword ptr [rsp+230h+var_1D0], ecx
0x18000b74a  lea     rcx, [rbp+130h+var_1B0]; struct _UNICODE_STRING *
0x18000b74e  mov     dword ptr [rsp+230h+var_1D8], edx
0x18000b752  lea     rdx, aPhysicaldriveU_0; "\\\\?\\PhysicalDrive%u \\\\?\\Disk{%08x"...
0x18000b759  mov     dword ptr [rsp+230h+var_1E0], r8d
0x18000b75e  mov     r8d, [r13+10h]
0x18000b762  mov     dword ptr [rsp+230h+var_1E8], r9d
0x18000b767  mov     r9d, [r14]
0x18000b76a  mov     [rsp+230h+var_1F0], r10d
0x18000b76f  mov     [rsp+230h+var_1F8], r11d
0x18000b774  mov     [rsp+230h+var_200], ebx
0x18000b778  mov     dword ptr [rsp+230h+var_208], edi
0x18000b77c  mov     [rsp+230h+var_210], esi
0x18000b780  mov     qword ptr [rbp+130h+var_1B0.Length], 0F00000h
0x18000b788  call    ?RtlUnicodeStringPrintf@@YAJPEAU_UNICODE_STRING@@PEBGZZ; RtlUnicodeStringPrintf(_UNICODE_STRING *,ushort const *,...)
0x18000b78d  mov     ebx, [rbp+130h+arg_28]
0x18000b793  mov     edi, 8
0x18000b798  test    ebx, ebx
0x18000b79a  js      short loc_18000B7BB
0x18000b79c  cmp     [rbp+130h+arg_30], 0
0x18000b7a3  jnz     loc_18000B887
0x18000b7a9  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, dil
0x18000b7b0  jz      short loc_18000B806
0x18000b7b2  lea     rdx, DISCANCR_EVENT_VOLUME_DRT_CLEAR
0x18000b7b9  jmp     short loc_18000B7CB
0x18000b7bb  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 10h
0x18000b7c2  jz      short loc_18000B806
0x18000b7c4  lea     rdx, DISCANCR_EVENT_VOLUME_DRT_CLEAR_WITH_ERROR
0x18000b7cb  movzx   r8d, [rbp+130h+var_1B0.Length]
0x18000b7d0  lea     rax, [r15+10h]
0x18000b7d4  mov     r9, [rbp+130h+var_1B0.Buffer]
0x18000b7d8  mov     [rsp+230h+var_1C8], rax
0x18000b7dd  mov     eax, [r13+10h]
0x18000b7e1  mov     [rsp+230h+var_1D0], r15
0x18000b7e6  mov     [rsp+230h+var_1D8], r14
0x18000b7eb  mov     [rsp+230h+var_1E0], r14
0x18000b7f0  mov     [rsp+230h+var_1E8], r12
0x18000b7f5  mov     [rsp+230h+var_1F8], eax
0x18000b7f9  shr     r8w, 1
0x18000b7fd  mov     [rsp+230h+var_200], ebx
0x18000b801  call    McTemplateU0hzr0hzr2dqiijjjj_EventWriteTransfer
0x18000b806  mov     eax, cs:dword_1800470B8
0x18000b80c  cmp     eax, 5
0x18000b80f  jbe     short loc_18000B887
0x18000b811  call    _tlgKeywordOn
0x18000b816  test    al, al
0x18000b818  jz      short loc_18000B887
0x18000b81a  lea     rax, [rbp+130h+var_198]
0x18000b81e  mov     [rbp+130h+var_198], r12
0x18000b822  mov     [rbp+130h+var_140], rax
0x18000b826  lea     rdx, byte_1800409DB
0x18000b82d  lea     rax, [rbp+130h+var_1B0]
0x18000b831  mov     qword ptr [rbp+130h+var_1B0.Length], 0
0x18000b839  mov     [rbp+130h+var_150], rax
0x18000b83d  lea     rcx, dword_1800470B8
0x18000b844  lea     rax, [rbp+130h+var_1A0]
0x18000b848  mov     [rbp+130h+var_1A0], ebx
0x18000b84b  mov     [rbp+130h+var_160], rax
0x18000b84f  xor     r9d, r9d
0x18000b852  lea     rax, [rbp+130h+var_190]
0x18000b856  mov     [rbp+130h+var_138], rdi
0x18000b85a  mov     [rsp+230h+var_208], rax
0x18000b85f  xor     r8d, r8d
0x18000b862  mov     [rsp+230h+var_210], 6
0x18000b86a  mov     [rbp+130h+var_148], rdi
0x18000b86e  mov     [rbp+130h+var_158], 4
0x18000b876  mov     [rbp+130h+var_170], r14
0x18000b87a  mov     [rbp+130h+var_168], 10h
0x18000b882  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b887  mov     rcx, [rbp+130h+var_40]
0x18000b88e  xor     rcx, rsp; StackCookie
0x18000b891  call    __security_check_cookie
0x18000b896  mov     rbx, [rsp+230h+arg_0]
0x18000b89e  add     rsp, 200h
0x18000b8a5  pop     r15
0x18000b8a7  pop     r14
0x18000b8a9  pop     r13
0x18000b8ab  pop     r12
0x18000b8ad  pop     rdi
0x18000b8ae  pop     rsi
0x18000b8af  pop     rbp
0x18000b8b0  retn
```
