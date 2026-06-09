# EventWriteDiskScanComplete(_SCRUB_ENVIRONMENT *,_STORAGE_DEVICE_NUMBER_EX const *,SPACEPORT_DISK_INFO const *,int)

- ea: `0x18000aaec`
- end: `0x18000ac2b`
- name: `?EventWriteDiskScanComplete@@YAXPEAU_SCRUB_ENVIRONMENT@@PEBU_STORAGE_DEVICE_NUMBER_EX@@PEBUSPACEPORT_DISK_INFO@@H@Z`
- size: `319`
- prototype: `void __fastcall(struct _SCRUB_ENVIRONMENT *, const struct _STORAGE_DEVICE_NUMBER_EX *, const struct SPACEPORT_DISK_INFO *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001cba8`
- `0x18001ce8c`

## callees

- `0x180001070`
- `0x18000166c`
- `0x18000aaec`
- `0x180011c8c`

## pseudocode

```c
void __fastcall EventWriteDiskScanComplete(
        struct _SCRUB_ENVIRONMENT *a1,
        const struct _STORAGE_DEVICE_NUMBER_EX *a2,
        const struct SPACEPORT_DISK_INFO *a3,
        int a4)
{
  const struct _STORAGE_DEVICE_NUMBER_EX *v5; // r8
  GUID *p_DeviceGuid; // rdi
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int16 *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  _QWORD v15[2]; // [rsp+30h] [rbp-10h] BYREF
  GUID *v16; // [rsp+50h] [rbp+10h] BYREF

  v5 = a2;
  if ( *((_DWORD *)a1 + 2) )
  {
    if ( a4 == 1 )
    {
      if ( (unsigned int)dword_1800470B8 > 5 && (unsigned __int8)tlgKeywordOn(a1, a2, a2) )
      {
        v16 = (GUID *)(v13 + 20);
        v15[0] = (char *)a1 + 52;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
          v12,
          (__int64)byte_1800412ED,
          v13,
          v14,
          v15,
          &v16);
      }
    }
    else
    {
      p_DeviceGuid = &a2->DeviceGuid;
      if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
        McTemplateU0qjjj_EventWriteTransfer(
          (_DWORD)a1,
          (unsigned int)DISCANCR_EVENT_DISK_SCAN_COMPLETE,
          a2->DeviceNumber,
          (_DWORD)p_DeviceGuid,
          (__int64)a3,
          (__int64)a3 + 16);
      if ( (unsigned int)dword_1800470B8 > 5 && (unsigned __int8)tlgKeywordOn(a1, a2, v5) )
      {
        v11 = (__int16 *)byte_1800412A9;
        goto LABEL_16;
      }
    }
  }
  else
  {
    p_DeviceGuid = &a2->DeviceGuid;
    if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 1) != 0 )
      McTemplateU0qjjj_EventWriteTransfer(
        (_DWORD)a1,
        (unsigned int)DISCAN_EVENT_DISK_SCAN_COMPLETE,
        a2->DeviceNumber,
        (_DWORD)p_DeviceGuid,
        (__int64)a3,
        (__int64)a3 + 16);
    if ( (unsigned int)dword_1800470B8 > 5 && (unsigned __int8)tlgKeywordOn(a1, a2, v5) )
    {
      v11 = word_18004132A;
LABEL_16:
      v15[0] = (char *)a1 + 52;
      v16 = p_DeviceGuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
        v8,
        (__int64)v11,
        v9,
        v10,
        v15,
        &v16);
    }
  }
}

```

## disassembly

```asm
0x18000aaec  mov     r11, rsp
0x18000aaef  mov     [r11+10h], rbx
0x18000aaf3  mov     [r11+18h], rdi
0x18000aaf7  push    rbp
0x18000aaf8  mov     rbp, rsp
0x18000aafb  sub     rsp, 40h
0x18000aaff  cmp     dword ptr [rcx+8], 0
0x18000ab03  mov     r10, r8
0x18000ab06  mov     r8, rdx
0x18000ab09  mov     rbx, rcx
0x18000ab0c  jnz     short loc_18000AB62
0x18000ab0e  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 1
0x18000ab15  lea     rdi, [rdx+14h]
0x18000ab19  jz      short loc_18000AB3A
0x18000ab1b  mov     r8d, [rdx+10h]
0x18000ab1f  lea     rax, [r10+10h]
0x18000ab23  mov     [r11-20h], rax
0x18000ab27  lea     rdx, DISCAN_EVENT_DISK_SCAN_COMPLETE
0x18000ab2e  mov     r9, rdi
0x18000ab31  mov     [r11-28h], r10
0x18000ab35  call    McTemplateU0qjjj_EventWriteTransfer
0x18000ab3a  mov     eax, cs:dword_1800470B8
0x18000ab40  cmp     eax, 5
0x18000ab43  jbe     loc_18000AC1B
0x18000ab49  call    _tlgKeywordOn
0x18000ab4e  test    al, al
0x18000ab50  jz      loc_18000AC1B
0x18000ab56  lea     rdx, word_18004132A
0x18000ab5d  jmp     loc_18000ABF8
0x18000ab62  cmp     r9d, 1
0x18000ab66  jnz     short loc_18000ABAF
0x18000ab68  mov     eax, cs:dword_1800470B8
0x18000ab6e  cmp     eax, 5
0x18000ab71  jbe     loc_18000AC1B
0x18000ab77  call    _tlgKeywordOn
0x18000ab7c  test    al, al
0x18000ab7e  jz      loc_18000AC1B
0x18000ab84  lea     rax, [r8+14h]
0x18000ab88  mov     [rbp+arg_0], rax
0x18000ab8c  lea     rdx, byte_1800412ED
0x18000ab93  lea     rax, [rbx+34h]
0x18000ab97  mov     [rbp+var_10], rax
0x18000ab9b  lea     rax, [rbp+arg_0]
0x18000ab9f  mov     [rsp+40h+var_18], rax
0x18000aba4  lea     rax, [rbp+var_10]
0x18000aba8  mov     [rsp+40h+var_20], rax
0x18000abad  jmp     short loc_18000AC16
0x18000abaf  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 8
0x18000abb6  lea     rdi, [rdx+14h]
0x18000abba  jz      short loc_18000ABDD
0x18000abbc  mov     r8d, [rdx+10h]
0x18000abc0  lea     rax, [r10+10h]
0x18000abc4  mov     [rsp+40h+var_18], rax
0x18000abc9  lea     rdx, DISCANCR_EVENT_DISK_SCAN_COMPLETE
0x18000abd0  mov     r9, rdi
0x18000abd3  mov     [rsp+40h+var_20], r10
0x18000abd8  call    McTemplateU0qjjj_EventWriteTransfer
0x18000abdd  mov     eax, cs:dword_1800470B8
0x18000abe3  cmp     eax, 5
0x18000abe6  jbe     short loc_18000AC1B
0x18000abe8  call    _tlgKeywordOn
0x18000abed  test    al, al
0x18000abef  jz      short loc_18000AC1B
0x18000abf1  lea     rdx, byte_1800412A9
0x18000abf8  lea     rax, [rbx+34h]
0x18000abfc  mov     [rbp+var_10], rax
0x18000ac00  lea     rax, [rbp+arg_0]
0x18000ac04  mov     [rsp+40h+var_18], rax
0x18000ac09  lea     rax, [rbp+var_10]
0x18000ac0d  mov     [rsp+40h+var_20], rax
0x18000ac12  mov     [rbp+arg_0], rdi
0x18000ac16  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &)
0x18000ac1b  mov     rbx, [rsp+40h+arg_8]
0x18000ac20  mov     rdi, [rsp+40h+arg_10]
0x18000ac25  add     rsp, 40h
0x18000ac29  pop     rbp
0x18000ac2a  retn
```
