# EventWriteDiskScanStart(_SCRUB_ENVIRONMENT *,_STORAGE_DEVICE_NUMBER_EX const *,SPACEPORT_DISK_INFO const *)

- ea: `0x18000ac34`
- end: `0x18000ad09`
- name: `?EventWriteDiskScanStart@@YAXPEAU_SCRUB_ENVIRONMENT@@PEBU_STORAGE_DEVICE_NUMBER_EX@@PEBUSPACEPORT_DISK_INFO@@@Z`
- size: `213`
- prototype: `void __fastcall(struct _SCRUB_ENVIRONMENT *, const struct _STORAGE_DEVICE_NUMBER_EX *, const struct SPACEPORT_DISK_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001cba8`

## callees

- `0x180001070`
- `0x18000166c`
- `0x18000ac34`
- `0x180011c8c`

## pseudocode

```c
void __fastcall EventWriteDiskScanStart(
        struct _SCRUB_ENVIRONMENT *a1,
        const struct _STORAGE_DEVICE_NUMBER_EX *a2,
        const struct SPACEPORT_DISK_INFO *a3)
{
  GUID *p_DeviceGuid; // rbx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  int *v8; // rdx
  GUID *v9; // [rsp+40h] [rbp+8h] BYREF
  char *v10; // [rsp+58h] [rbp+20h] BYREF

  p_DeviceGuid = &a2->DeviceGuid;
  if ( *((_DWORD *)a1 + 2) )
  {
    if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
      McTemplateU0qjjj_EventWriteTransfer(
        (_DWORD)a1,
        (unsigned int)DISCANCR_EVENT_DISK_SCAN_START,
        a2->DeviceNumber,
        (_DWORD)a2 + 20,
        (__int64)a3,
        (__int64)a3 + 16);
    if ( (unsigned int)dword_1800470B8 > 5 && (unsigned __int8)tlgKeywordOn(a1, a2, a3) )
    {
      v8 = &dword_18004136C;
      goto LABEL_12;
    }
  }
  else
  {
    if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 1) != 0 )
      McTemplateU0qjjj_EventWriteTransfer(
        (_DWORD)a1,
        (unsigned int)DISCAN_EVENT_DISK_SCAN_START,
        a2->DeviceNumber,
        (_DWORD)a2 + 20,
        (__int64)a3,
        (__int64)a3 + 16);
    if ( (unsigned int)dword_1800470B8 > 5 && (unsigned __int8)tlgKeywordOn(a1, a2, a3) )
    {
      v8 = (int *)byte_1800413AD;
LABEL_12:
      v10 = (char *)a1 + 52;
      v9 = p_DeviceGuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
        v5,
        (__int64)v8,
        v6,
        v7,
        &v10,
        &v9);
    }
  }
}

```

## disassembly

```asm
0x18000ac34  mov     [rsp+arg_8], rbx
0x18000ac39  push    rdi
0x18000ac3a  sub     rsp, 30h
0x18000ac3e  cmp     dword ptr [rcx+8], 0
0x18000ac42  lea     rbx, [rdx+14h]
0x18000ac46  mov     rdi, rcx
0x18000ac49  jnz     short loc_18000AC92
0x18000ac4b  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 1
0x18000ac52  jz      short loc_18000AC75
0x18000ac54  lea     rax, [r8+10h]
0x18000ac58  mov     r9, rbx
0x18000ac5b  mov     [rsp+38h+var_10], rax
0x18000ac60  mov     [rsp+38h+var_18], r8
0x18000ac65  mov     r8d, [rdx+10h]
0x18000ac69  lea     rdx, DISCAN_EVENT_DISK_SCAN_START
0x18000ac70  call    McTemplateU0qjjj_EventWriteTransfer
0x18000ac75  mov     eax, cs:dword_1800470B8
0x18000ac7b  cmp     eax, 5
0x18000ac7e  jbe     short loc_18000ACFE
0x18000ac80  call    _tlgKeywordOn
0x18000ac85  test    al, al
0x18000ac87  jz      short loc_18000ACFE
0x18000ac89  lea     rdx, byte_1800413AD
0x18000ac90  jmp     short loc_18000ACD7
0x18000ac92  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 8
0x18000ac99  jz      short loc_18000ACBC
0x18000ac9b  lea     rax, [r8+10h]
0x18000ac9f  mov     r9, rbx
0x18000aca2  mov     [rsp+38h+var_10], rax
0x18000aca7  mov     [rsp+38h+var_18], r8
0x18000acac  mov     r8d, [rdx+10h]
0x18000acb0  lea     rdx, DISCANCR_EVENT_DISK_SCAN_START
0x18000acb7  call    McTemplateU0qjjj_EventWriteTransfer
0x18000acbc  mov     eax, cs:dword_1800470B8
0x18000acc2  cmp     eax, 5
0x18000acc5  jbe     short loc_18000ACFE
0x18000acc7  call    _tlgKeywordOn
0x18000accc  test    al, al
0x18000acce  jz      short loc_18000ACFE
0x18000acd0  lea     rdx, dword_18004136C
0x18000acd7  lea     rax, [rdi+34h]
0x18000acdb  mov     [rsp+38h+arg_18], rax
0x18000ace0  lea     rax, [rsp+38h+arg_0]
0x18000ace5  mov     [rsp+38h+var_10], rax
0x18000acea  lea     rax, [rsp+38h+arg_18]
0x18000acef  mov     [rsp+38h+var_18], rax
0x18000acf4  mov     [rsp+38h+arg_0], rbx
0x18000acf9  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &)
0x18000acfe  mov     rbx, [rsp+38h+arg_8]
0x18000ad03  add     rsp, 30h
0x18000ad07  pop     rdi
0x18000ad08  retn
```
