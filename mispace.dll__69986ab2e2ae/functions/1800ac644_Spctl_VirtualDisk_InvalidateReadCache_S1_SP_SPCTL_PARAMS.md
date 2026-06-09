# Spctl_VirtualDisk_InvalidateReadCache_S1(_SP_SPCTL_PARAMS *)

- ea: `0x1800ac644`
- end: `0x1800aca06`
- name: `?Spctl_VirtualDisk_InvalidateReadCache_S1@@YAKPEAU_SP_SPCTL_PARAMS@@@Z`
- size: `962`
- prototype: `unsigned int __fastcall(struct _SP_SPCTL_PARAMS *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800958b8`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x18000cd3c`
- `0x18000f484`
- `0x180013d34`
- `0x1800198f4`
- `0x18001b608`
- `0x180026a6c`
- `0x1800ac644`
- `0x1800aef0c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac7e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac7e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ac807`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ac807`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ac748`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ac748`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800ac964`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800ac964`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ac8fb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ac8fb`

## string_xrefs

- `0x1800ac65c`: `Spctl_VirtualDisk_InvalidateReadCache_S1`
- `0x1800ac773`: `Spctl_VirtualDisk_InvalidateReadCache_S1`
- `0x1800ac81e`: `Spctl_VirtualDisk_InvalidateReadCache_S1`
- `0x1800ac89d`: `Spctl_VirtualDisk_InvalidateReadCache_S1`

## pseudocode

```c
__int64 __fastcall Spctl_VirtualDisk_InvalidateReadCache_S1(struct _SP_SPCTL_PARAMS *a1, __int64 a2, int a3, int a4)
{
  __int64 v6; // r13
  __int128 v7; // xmm1
  __int64 FileW; // r15
  WCHAR *v9; // rdi
  enum _MI_Result VolumeOnVirtualDisk; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // r8d
  int v14; // r9d
  const unsigned __int16 *v15; // r14
  __int64 v16; // rbx
  unsigned __int64 v17; // rbx
  unsigned __int16 *v18; // rax
  int v19; // ecx
  char *v20; // rdx
  __int64 v21; // rbx
  unsigned int v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  unsigned int v26; // ecx
  char *v27; // rdx
  int LastError; // eax
  int v29; // eax
  _OWORD v30[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v31; // [rsp+60h] [rbp-10h] BYREF
  char v32; // [rsp+68h] [rbp-8h]
  int v33; // [rsp+B0h] [rbp+40h] BYREF
  const char *v34; // [rsp+B8h] [rbp+48h] BYREF
  DWORD BytesReturned; // [rsp+C0h] [rbp+50h] BYREF
  MI_Instance *self; // [rsp+C8h] [rbp+58h] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v33 = 5844;
    v34 = "Spctl_VirtualDisk_InvalidateReadCache_S1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)byte_180320251,
      a3,
      a4,
      (__int64)&v34,
      (__int64)&v33);
  }
  BytesReturned = 0;
  self = 0;
  v31 = 0;
  v32 = 0;
  if ( *((_DWORD *)a1 + 146) < 0x220u )
  {
    **((_DWORD **)a1 + 74) = 544;
    return 87;
  }
  v6 = *((_QWORD *)a1 + 72);
  v7 = *(_OWORD *)((char *)a1 + 20);
  FileW = -1;
  v30[0] = *(_OWORD *)((char *)a1 + 4);
  v9 = 0;
  v30[1] = v7;
  VolumeOnVirtualDisk = GetVolumeOnVirtualDisk((struct _SP_ID *)v30, &self);
  if ( VolumeOnVirtualDisk )
  {
    v26 = VolumeOnVirtualDisk | 0x85200000;
    LODWORD(v31) = v26;
    if ( (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_14;
    v33 = v26;
    v27 = (char *)word_1803248AA;
    LODWORD(v34) = 5865;
    *(_QWORD *)&v30[0] = "Spctl_VirtualDisk_InvalidateReadCache_S1";
    goto LABEL_27;
  }
  LODWORD(v31) = 85983232;
  v15 = *(const unsigned __int16 **)(SmMIGetInstance(v30, L"Path", self) + 8);
  if ( !v15 || !*v15 )
  {
    v19 = -2060451835;
    LODWORD(v31) = -2060451835;
    if ( (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_14;
    LODWORD(v34) = 5874;
    v20 = (char *)&unk_180325260;
    *(_QWORD *)&v30[0] = "Spctl_VirtualDisk_InvalidateReadCache_S1";
    goto LABEL_13;
  }
  v16 = -1;
  do
    ++v16;
  while ( v15[v16] );
  v17 = v16 + 1;
  v18 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v17);
  v9 = v18;
  if ( v18 )
  {
    if ( (int)StringCchCopyW(v18, v17, v15) >= 0 )
    {
      if ( v9[v17 - 2] == 92 )
        v9[v17 - 2] = 0;
      FileW = (__int64)CreateFileW(v9, 0x80000000, 3u, 0, 3u, 0, 0);
      if ( FileW == -1 )
      {
        LastError = _status_t::GetLastError((_status_t *)&v31);
        v26 = dword_18039EB68;
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_14;
        v33 = LastError;
        v27 = &byte_180322907;
        LODWORD(v34) = 5914;
      }
      else
      {
        if ( DeviceIoControl((HANDLE)FileW, 0x9039Cu, 0, 0, 0, 0, &BytesReturned, 0) )
          goto LABEL_14;
        v29 = _status_t::GetLastError((_status_t *)&v31);
        v26 = dword_18039EB68;
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_14;
        v33 = v29;
        v27 = (char *)&unk_180323C70;
        LODWORD(v34) = 5928;
      }
    }
    else
    {
      v26 = -2060451835;
      LODWORD(v31) = -2060451835;
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_14;
      v33 = -2060451835;
      v27 = byte_1803295F3;
      LODWORD(v34) = 5891;
    }
    *(_QWORD *)&v30[0] = "Spctl_VirtualDisk_InvalidateReadCache_S1";
LABEL_27:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v26,
      (_DWORD)v27,
      v11,
      v12,
      (__int64)v30,
      (__int64)&v34,
      (__int64)&v33);
    goto LABEL_14;
  }
  v19 = -2060411838;
  LODWORD(v31) = -2060411838;
  if ( (unsigned int)dword_18039EB68 > 2 )
  {
    LODWORD(v34) = 5885;
    *(_QWORD *)&v30[0] = "Spctl_VirtualDisk_InvalidateReadCache_S1";
    v20 = byte_180324705;
LABEL_13:
    v33 = v19;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v19,
      (_DWORD)v20,
      v13,
      v14,
      (__int64)v30,
      (__int64)&v34,
      (__int64)&v33);
  }
LABEL_14:
  v21 = *((_QWORD *)a1 + 74);
  v22 = _status_t::ToSMRC(&v31);
  _FillMethodResponse(v6, *((unsigned int *)a1 + 146), v22, 0, v21);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( self )
    MI_Instance_Delete(self);
  if ( v9 )
    LocalFree(v9);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v33 = 5950;
    v34 = "Spctl_VirtualDisk_InvalidateReadCache_S1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)&byte_1803243AF,
      v24,
      v25,
      (__int64)&v34,
      (__int64)&v33);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ac644  push    rbp
0x1800ac646  push    rbx
0x1800ac647  push    rsi
0x1800ac648  push    rdi
0x1800ac649  push    r13
0x1800ac64b  push    r14
0x1800ac64d  push    r15
0x1800ac64f  mov     rbp, rsp
0x1800ac652  sub     rsp, 70h
0x1800ac656  mov     eax, cs:dword_18039EB68
0x1800ac65c  lea     rbx, aSpctlVirtualdi_35; "Spctl_VirtualDisk_InvalidateReadCache_S"...
0x1800ac663  mov     rsi, rcx
0x1800ac666  cmp     eax, 5
0x1800ac669  jbe     short loc_1800AC694
0x1800ac66b  lea     rax, [rbp+arg_0]
0x1800ac66f  mov     [rbp+arg_0], 16D4h
0x1800ac676  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x1800ac67b  lea     rdx, byte_180320251
0x1800ac682  lea     rax, [rbp+arg_8]
0x1800ac686  mov     [rbp+arg_8], rbx
0x1800ac68a  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800ac68f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ac694  xor     r14d, r14d
0x1800ac697  mov     ecx, 220h
0x1800ac69c  mov     [rbp+BytesReturned], r14d
0x1800ac6a0  mov     [rbp+self], r14
0x1800ac6a4  mov     [rbp+var_10], r14
0x1800ac6a8  mov     [rbp+var_8], r14b
0x1800ac6ac  cmp     [rsi+248h], ecx
0x1800ac6b2  jnb     short loc_1800AC6C6
0x1800ac6b4  mov     rax, [rsi+250h]
0x1800ac6bb  mov     [rax], ecx
0x1800ac6bd  lea     eax, [r14+57h]
0x1800ac6c1  jmp     loc_1800AC850
0x1800ac6c6  movups  xmm0, xmmword ptr [rsi+4]
0x1800ac6ca  mov     r13, [rsi+240h]
0x1800ac6d1  lea     rdx, [rbp+self]; struct _MI_Instance **
0x1800ac6d5  movups  xmm1, xmmword ptr [rsi+14h]
0x1800ac6d9  lea     rcx, [rbp+var_30]; struct _SP_ID *
0x1800ac6dd  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800ac6e1  movups  [rbp+var_30], xmm0
0x1800ac6e5  mov     rdi, r14
0x1800ac6e8  movups  [rbp+var_20], xmm1
0x1800ac6ec  call    ?GetVolumeOnVirtualDisk@@YA?AW4_MI_Result@@PEAU_SP_ID@@PEAPEAU_MI_Instance@@@Z; GetVolumeOnVirtualDisk(_SP_ID *,_MI_Instance * *)
0x1800ac6f1  mov     ecx, eax
0x1800ac6f3  test    eax, eax
0x1800ac6f5  jnz     loc_1800AC9D4
0x1800ac6fb  mov     r8, [rbp+self]
0x1800ac6ff  lea     rdx, aPath; "Path"
0x1800ac706  lea     rcx, [rbp+var_30]
0x1800ac70a  mov     dword ptr [rbp+var_10], 5200000h
0x1800ac711  call    ?SmMIGetInstance@@YA?AV?$Nullable@PEAU_MI_Instance@@@@PEBGPEBU_MI_Instance@@@Z; SmMIGetInstance(ushort const *,_MI_Instance const *)
0x1800ac716  mov     r14, [rax+8]
0x1800ac71a  xor     eax, eax
0x1800ac71c  test    r14, r14
0x1800ac71f  jz      loc_1800AC9A6
0x1800ac725  cmp     [r14], ax
0x1800ac729  jz      loc_1800AC9A6
0x1800ac72f  or      rbx, r15
0x1800ac732  inc     rbx
0x1800ac735  cmp     [r14+rbx*2], ax
0x1800ac73a  jnz     short loc_1800AC732
0x1800ac73c  inc     rbx
0x1800ac73f  mov     ecx, 40h ; '@'; uFlags
0x1800ac744  lea     rdx, [rbx+rbx]; uBytes
0x1800ac748  call    cs:__imp_LocalAlloc
0x1800ac74f  nop     dword ptr [rax+rax+00h]
0x1800ac754  mov     rdi, rax
0x1800ac757  test    rax, rax
0x1800ac75a  jnz     loc_1800AC860
0x1800ac760  mov     eax, cs:dword_18039EB68
0x1800ac766  mov     ecx, 85309C42h
0x1800ac76b  mov     dword ptr [rbp+var_10], ecx
0x1800ac76e  cmp     eax, 2
0x1800ac771  jbe     short loc_1800AC7AF
0x1800ac773  lea     rax, aSpctlVirtualdi_35; "Spctl_VirtualDisk_InvalidateReadCache_S"...
0x1800ac77a  mov     dword ptr [rbp+arg_8], 16FDh
0x1800ac781  mov     qword ptr [rbp+var_30], rax
0x1800ac785  lea     rdx, byte_180324705
0x1800ac78c  lea     rax, [rbp+arg_0]
0x1800ac790  mov     [rsp+70h+hTemplateFile], rax
0x1800ac795  lea     rax, [rbp+arg_8]
0x1800ac799  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x1800ac79e  lea     rax, [rbp+var_30]
0x1800ac7a2  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800ac7a7  mov     [rbp+arg_0], ecx
0x1800ac7aa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ac7af  xor     r14d, r14d
0x1800ac7b2  mov     rbx, [rsi+250h]
0x1800ac7b9  lea     rcx, [rbp+var_10]
0x1800ac7bd  call    ?ToSMRC@_status_t@@QEAA?AW4SM_RETURN_CODE@@XZ; _status_t::ToSMRC(void)
0x1800ac7c2  mov     edx, [rsi+248h]
0x1800ac7c8  xor     r9d, r9d
0x1800ac7cb  mov     r8d, eax
0x1800ac7ce  mov     qword ptr [rsp+70h+dwCreationDisposition], rbx
0x1800ac7d3  mov     rcx, r13
0x1800ac7d6  call    ?_FillMethodResponse@@YAXPEAEKW4SM_RETURN_CODE@@PEAU_SUEX_EXTENDEDSTATUS_OBJECT@@PEAK@Z; _FillMethodResponse(uchar *,ulong,SM_RETURN_CODE,_SUEX_EXTENDEDSTATUS_OBJECT *,ulong *)
0x1800ac7db  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800ac7df  jz      short loc_1800AC7F0
0x1800ac7e1  mov     rcx, r15; hObject
0x1800ac7e4  call    cs:__imp_CloseHandle
0x1800ac7eb  nop     dword ptr [rax+rax+00h]
0x1800ac7f0  cmp     [rbp+self], r14
0x1800ac7f4  jz      short loc_1800AC7FF
0x1800ac7f6  mov     rcx, [rbp+self]; self
0x1800ac7fa  call    MI_Instance_Delete
0x1800ac7ff  test    rdi, rdi
0x1800ac802  jz      short loc_1800AC813
0x1800ac804  mov     rcx, rdi; hMem
0x1800ac807  call    cs:__imp_LocalFree
0x1800ac80e  nop     dword ptr [rax+rax+00h]
0x1800ac813  mov     eax, cs:dword_18039EB68
0x1800ac819  cmp     eax, 5
0x1800ac81c  jbe     short loc_1800AC84E
0x1800ac81e  lea     rax, aSpctlVirtualdi_35; "Spctl_VirtualDisk_InvalidateReadCache_S"...
0x1800ac825  mov     [rbp+arg_0], 173Eh
0x1800ac82c  mov     [rbp+arg_8], rax
0x1800ac830  lea     rdx, byte_1803243AF
0x1800ac837  lea     rax, [rbp+arg_0]
0x1800ac83b  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x1800ac840  lea     rax, [rbp+arg_8]
0x1800ac844  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800ac849  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ac84e  xor     eax, eax
0x1800ac850  add     rsp, 70h
0x1800ac854  pop     r15
0x1800ac856  pop     r14
0x1800ac858  pop     r13
0x1800ac85a  pop     rdi
0x1800ac85b  pop     rsi
0x1800ac85c  pop     rbx
0x1800ac85d  pop     rbp
0x1800ac85e  retn
0x1800ac860  mov     r8, r14; unsigned __int16 *
0x1800ac863  mov     rdx, rbx; unsigned __int64
0x1800ac866  mov     rcx, rdi; unsigned __int16 *
0x1800ac869  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ac86e  xor     r14d, r14d
0x1800ac871  test    eax, eax
0x1800ac873  jns     short loc_1800AC8CD
0x1800ac875  mov     eax, cs:dword_18039EB68
0x1800ac87b  mov     ecx, 85300005h
0x1800ac880  mov     dword ptr [rbp+var_10], ecx
0x1800ac883  cmp     eax, 2
0x1800ac886  jbe     loc_1800AC7B2
0x1800ac88c  mov     [rbp+arg_0], ecx
0x1800ac88f  lea     rdx, byte_1803295F3
0x1800ac896  mov     dword ptr [rbp+arg_8], 1703h
0x1800ac89d  lea     rax, aSpctlVirtualdi_35; "Spctl_VirtualDisk_InvalidateReadCache_S"...
0x1800ac8a4  mov     qword ptr [rbp+var_30], rax
0x1800ac8a8  lea     rax, [rbp+arg_0]
0x1800ac8ac  mov     [rsp+70h+hTemplateFile], rax
0x1800ac8b1  lea     rax, [rbp+arg_8]
0x1800ac8b5  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x1800ac8ba  lea     rax, [rbp+var_30]
0x1800ac8be  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800ac8c3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ac8c8  jmp     loc_1800AC7B2
0x1800ac8cd  cmp     word ptr [rdi+rbx*2-4], 5Ch ; '\'
0x1800ac8d3  jnz     short loc_1800AC8DB
0x1800ac8d5  mov     [rdi+rbx*2-4], r14w
0x1800ac8db  mov     [rsp+70h+hTemplateFile], r14; hTemplateFile
0x1800ac8e0  mov     r8d, 3; dwShareMode
0x1800ac8e6  mov     [rsp+70h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x1800ac8eb  xor     r9d, r9d; lpSecurityAttributes
0x1800ac8ee  mov     edx, 80000000h; dwDesiredAccess
0x1800ac8f3  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800ac8f8  mov     rcx, rdi; lpFileName
0x1800ac8fb  call    cs:__imp_CreateFileW
0x1800ac902  nop     dword ptr [rax+rax+00h]
0x1800ac907  mov     r15, rax
0x1800ac90a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ac90e  jnz     short loc_1800AC93E
0x1800ac910  lea     rcx, [rbp+var_10]; this
0x1800ac914  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x1800ac919  mov     ecx, cs:dword_18039EB68
0x1800ac91f  cmp     ecx, 2
0x1800ac922  jbe     loc_1800AC7B2
0x1800ac928  mov     [rbp+arg_0], eax
0x1800ac92b  lea     rdx, byte_180322907
0x1800ac932  mov     dword ptr [rbp+arg_8], 171Ah
0x1800ac939  jmp     loc_1800AC89D
0x1800ac93e  mov     [rsp+70h+lpOverlapped], r14; lpOverlapped
0x1800ac943  lea     rax, [rbp+BytesReturned]
0x1800ac947  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x1800ac94c  xor     r9d, r9d; nInBufferSize
0x1800ac94f  mov     [rsp+70h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x1800ac954  xor     r8d, r8d; lpInBuffer
0x1800ac957  mov     edx, 9039Ch; dwIoControlCode
0x1800ac95c  mov     qword ptr [rsp+70h+dwCreationDisposition], r14; lpOutBuffer
0x1800ac961  mov     rcx, r15; hDevice
0x1800ac964  call    cs:__imp_DeviceIoControl
0x1800ac96b  nop     dword ptr [rax+rax+00h]
0x1800ac970  test    eax, eax
0x1800ac972  jnz     loc_1800AC7B2
0x1800ac978  lea     rcx, [rbp+var_10]; this
0x1800ac97c  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x1800ac981  mov     ecx, cs:dword_18039EB68
0x1800ac987  cmp     ecx, 2
0x1800ac98a  jbe     loc_1800AC7B2
0x1800ac990  mov     [rbp+arg_0], eax
0x1800ac993  lea     rdx, unk_180323C70
0x1800ac99a  mov     dword ptr [rbp+arg_8], 1728h
0x1800ac9a1  jmp     loc_1800AC89D
0x1800ac9a6  mov     eax, cs:dword_18039EB68
0x1800ac9ac  mov     ecx, 85300005h
0x1800ac9b1  mov     dword ptr [rbp+var_10], ecx
0x1800ac9b4  cmp     eax, 2
0x1800ac9b7  jbe     loc_1800AC7AF
0x1800ac9bd  mov     dword ptr [rbp+arg_8], 16F2h
0x1800ac9c4  lea     rdx, unk_180325260
0x1800ac9cb  mov     qword ptr [rbp+var_30], rbx
0x1800ac9cf  jmp     loc_1800AC78C
0x1800ac9d4  mov     eax, cs:dword_18039EB68
0x1800ac9da  or      ecx, 85200000h
0x1800ac9e0  mov     dword ptr [rbp+var_10], ecx
0x1800ac9e3  cmp     eax, 2
0x1800ac9e6  jbe     loc_1800AC7B2
0x1800ac9ec  mov     [rbp+arg_0], ecx
0x1800ac9ef  lea     rdx, word_1803248AA
0x1800ac9f6  mov     dword ptr [rbp+arg_8], 16E9h
0x1800ac9fd  mov     qword ptr [rbp+var_30], rbx
0x1800aca01  jmp     loc_1800AC8A8
```
