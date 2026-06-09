# CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy(CMap<ushort *,unsigned __int64> *)

- ea: `0x1800d13a0`
- end: `0x1800d18d1`
- name: `?_WaitForRegenerationLegacy@RemovePhysicalDisk@CSpStoragePool@@AEAAXPEAV?$CMap@PEAG_K@@@Z`
- size: `1329`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x1800ce2a8`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x180006290`
- `0x18001f294`
- `0x180023508`
- `0x18002bdb0`
- `0x180047998`
- `0x180051508`
- `0x18005f594`
- `0x18006068c`
- `0x1800677b0`
- `0x180074e54`
- `0x180092ca4`
- `0x1800d13a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d154f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d16a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d154f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d16a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d14bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d16e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d16f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d14bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d16e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d16f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d180d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d185a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d180d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d185a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d17ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d17ab`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800d1846`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800d1846`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800d17f8`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800d17f8`

## string_xrefs

- `0x1800d13e0`: `CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy`
- `0x1800d1518`: `CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy`
- `0x1800d174d`: `CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy`
- `0x1800d1860`: `CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int16 v6; // r13
  unsigned __int64 v7; // rsi
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  DWORD LastError; // ebx
  __int64 v14; // r14
  __int64 v15; // rax
  __int64 v16; // rdi
  int Id; // eax
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // r9
  __int16 v22; // r12
  int v23; // r15d
  __int64 v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  char *v29; // rdx
  int v30; // edi
  BOOLEAN v31; // al
  __int64 v32; // rdx
  int v34; // [rsp+48h] [rbp-B8h]
  __int128 v35; // [rsp+50h] [rbp-B0h] BYREF
  int v36; // [rsp+60h] [rbp-A0h]
  HLOCAL hMem; // [rsp+68h] [rbp-98h]
  _QWORD Buffer[2]; // [rsp+70h] [rbp-90h] BYREF
  const char *v39; // [rsp+80h] [rbp-80h] BYREF
  PVOID v40[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v41; // [rsp+98h] [rbp-68h]
  __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v43; // [rsp+A8h] [rbp-58h]
  PVOID RestartKey[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v45; // [rsp+C8h] [rbp-38h]
  _OWORD v46[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE TableContext[8]; // [rsp+F0h] [rbp-10h] BYREF
  struct _RTL_AVL_TABLE Table; // [rsp+F8h] [rbp-8h] BYREF
  int v49; // [rsp+160h] [rbp+60h]
  _BYTE v50[512]; // [rsp+180h] [rbp+80h] BYREF

  v39 = (const char *)a1;
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    Buffer[0] = "CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)byte_1803286FB,
      a3,
      a4,
      Buffer);
  }
  v6 = 0;
  hMem = 0;
  v7 = 0;
  Buffer[0] = 0;
  v42 = 16;
  v43 = 0;
  v45 = 0;
  *(_OWORD *)RestartKey = 0;
  v41 = 0;
  *(_OWORD *)v40 = 0;
  CMap<unsigned short const *,_SUEX_SPACE_OBJECT *>::CMap<unsigned short const *,_SUEX_SPACE_OBJECT *>(TableContext);
  v8 = CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(a2, v46);
  *(_OWORD *)RestartKey = *(_OWORD *)v8;
  v45 = *(_QWORD *)(v8 + 16);
  while ( RestartKey[0] && RestartKey[1] )
  {
    v9 = *((_QWORD *)RestartKey[1] + 1);
    *(_QWORD *)&v43 = *(_QWORD *)RestartKey[1];
    if ( !(unsigned int)EnumerateAssociatedStorageObjects<_SUEX_JOB_OBJECT>(
                          (struct _SP_OBJECT_ID *)&v42,
                          (__int64)TableContext) )
    {
      if ( GetLastError() != 1168 )
        goto LABEL_56;
LABEL_11:
      CSpWmiMethod<_SPACES_VirtualDisk_Repair>::Update(a1, 100);
      goto LABEL_56;
    }
    v7 += v9;
    CMapIter<unsigned short const *,_SUEX_SPACE_OBJECT *>::Next(RestartKey);
  }
  if ( !v7 )
    goto LABEL_11;
  LastError = 0;
  v34 = 0;
  v14 = 0;
  v15 = CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(TableContext, v46);
  *(_OWORD *)v40 = *(_OWORD *)v15;
  v41 = *(_QWORD *)(v15 + 16);
  while ( v40[0] && v40[1] )
  {
    v16 = *((_QWORD *)v40[1] + 1);
    if ( !*(_WORD *)(v16 + 72) || !(unsigned int)_o__wcsicmp(v16 + *(unsigned __int16 *)(v16 + 72), L"Regeneration") )
    {
      v35 = *(_OWORD *)(v16 + 152);
      v46[0] = *(_OWORD *)(v16 + 24);
      Id = SuexCreateId(v50, *(unsigned int *)(v16 + 60), 16, v46);
      LastError = Id;
      if ( Id )
      {
        if ( Id > 0 )
          v18 = (unsigned __int16)Id | 0x80070000;
        else
          v18 = (unsigned int)Id;
        v19 = GleToSmpReturnCode(v18);
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          v36 = v19;
          *(_QWORD *)&v35 = "CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)dword_180397B68,
            (__int64)qword_18032CB78,
            v20,
            v21,
            &v35);
        }
      }
      else if ( (unsigned int)CMapBase<unsigned short *,unsigned short *>::Find(a2, v50, Buffer) )
      {
        *(_WORD *)(v16 + 88) = 100LL * Buffer[0] / v7;
      }
      else
      {
        *(_WORD *)(v16 + 88) = 0;
      }
    }
    CMapIter<unsigned short const *,_SUEX_SPACE_OBJECT *>::Next(v40);
  }
  v22 = 0;
LABEL_28:
  if ( v49 )
  {
    v23 = 0;
    LODWORD(v42) = 9;
    v24 = CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(TableContext, v46);
    *(_OWORD *)v40 = *(_OWORD *)v24;
    v41 = *(_QWORD *)(v24 + 16);
    while ( 1 )
    {
      if ( !v40[0] || !v40[1] )
      {
        if ( !v23 )
        {
          LOWORD(v30) = v34;
          goto LABEL_53;
        }
LABEL_49:
        HIWORD(v30) = HIWORD(v34);
        LOWORD(v30) = v22 + v34;
        v34 = v30;
        Buffer[0] = v14;
        Buffer[1] = 0;
        v31 = RtlDeleteElementGenericTableAvl(&Table, Buffer);
        if ( v31 )
          --v49;
        SetLastError(v31 == 0 ? 0x490 : 0);
LABEL_53:
        v32 = (unsigned int)(91 * (unsigned __int16)(v30 + v6) / 100);
        LOWORD(v32) = v32 + 9;
        CSpWmiMethod<_SPACES_VirtualDisk_Repair>::Update(v39, v32);
        Sleep(0x1388u);
        v6 = 0;
        goto LABEL_28;
      }
      v25 = *((_QWORD *)v40[1] + 1);
      if ( *(_WORD *)(v25 + 72) && (unsigned int)_o__wcsicmp(v25 + *(unsigned __int16 *)(v25 + 72), L"Regeneration") )
      {
        v14 = v25 + *(unsigned int *)(v25 + 56);
        v22 = 0;
        goto LABEL_49;
      }
      *(_QWORD *)&v43 = v25 + *(unsigned int *)(v25 + 56);
      if ( (unsigned int)GetStorageObject<_SUEX_JOB_OBJECT>((struct _SP_OBJECT_ID *)&v42) )
      {
        v6 += *(unsigned __int16 *)(v25 + 88) * *((unsigned __int16 *)hMem + 44) / 100;
        LocalFree(hMem);
        hMem = 0;
      }
      else
      {
        v23 = 1;
        v14 = v25 + *(unsigned int *)(v25 + 56);
        v22 = *(_WORD *)(v25 + 88);
        if ( GetLastError() == 1168 )
          goto LABEL_46;
        LastError = GetLastError();
        if ( LastError )
        {
          if ( LastError == 122 )
          {
            if ( (unsigned int)dword_180397B68 <= 3 )
              goto LABEL_46;
            v29 = byte_18032A93B;
          }
          else
          {
            if ( (unsigned int)dword_180397B68 <= 2 )
              goto LABEL_46;
            v29 = byte_1803285BD;
          }
        }
        else
        {
          if ( (unsigned int)dword_180397B68 <= 4 )
            goto LABEL_46;
          v29 = (char *)&dword_18032CADC;
        }
        *(_QWORD *)&v35 = "CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v26,
          (__int64)v29,
          v27,
          v28,
          &v35);
      }
LABEL_46:
      CMapIter<unsigned short const *,_SUEX_SPACE_OBJECT *>::Next(v40);
    }
  }
  if ( LastError )
    SetLastError(LastError);
LABEL_56:
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v39 = "CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v10,
      (__int64)&word_18032B376,
      v11,
      v12,
      &v39);
  }
  return CMap<unsigned short const *,_SUEX_NODE_OBJECT *>::~CMap<unsigned short const *,_SUEX_NODE_OBJECT *>(TableContext);
}

```

## disassembly

```asm
0x1800d13a0  mov     [rsp-8+arg_10], rbx
0x1800d13a5  push    rbp
0x1800d13a6  push    rsi
0x1800d13a7  push    rdi
0x1800d13a8  push    r12
0x1800d13aa  push    r13
0x1800d13ac  push    r14
0x1800d13ae  push    r15
0x1800d13b0  lea     rbp, [rsp-290h]
0x1800d13b8  sub     rsp, 390h
0x1800d13bf  mov     rax, cs:__security_cookie
0x1800d13c6  xor     rax, rsp
0x1800d13c9  mov     [rbp+2C0h+var_40], rax
0x1800d13d0  mov     r15, rdx
0x1800d13d3  mov     rdi, rcx
0x1800d13d6  mov     [rbp+2C0h+var_340], rcx
0x1800d13da  mov     eax, cs:dword_180397B68
0x1800d13e0  lea     r14, aCspstoragepool_10; "CSpStoragePool::RemovePhysicalDisk::_Wa"...
0x1800d13e7  cmp     eax, 5
0x1800d13ea  jbe     short loc_1800D1419
0x1800d13ec  mov     [rsp+3C0h+var_378], 1C5Ch
0x1800d13f4  mov     [rsp+3C0h+Buffer], r14
0x1800d13f9  lea     rax, [rsp+3C0h+var_378]
0x1800d13fe  mov     [rsp+3C0h+var_398], rax
0x1800d1403  lea     rax, [rsp+3C0h+Buffer]
0x1800d1408  mov     [rsp+3C0h+var_3A0], rax
0x1800d140d  lea     rdx, byte_1803286FB
0x1800d1414  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800d1419  xor     r13d, r13d
0x1800d141c  mov     [rsp+3C0h+hMem], r13
0x1800d1421  mov     esi, r13d
0x1800d1424  mov     [rsp+3C0h+Buffer], r13
0x1800d1429  mov     [rbp+2C0h+var_320], 10h
0x1800d1431  xorps   xmm0, xmm0
0x1800d1434  movdqu  [rbp+2C0h+var_318], xmm0
0x1800d1439  mov     [rbp+2C0h+var_2F8], r13
0x1800d143d  xorps   xmm1, xmm1
0x1800d1440  movdqu  xmmword ptr [rbp+2C0h+RestartKey], xmm1
0x1800d1445  mov     [rbp+2C0h+var_328], r13
0x1800d1449  movdqu  xmmword ptr [rbp+2C0h+var_338], xmm0
0x1800d144e  lea     rcx, [rbp+2C0h+TableContext]
0x1800d1452  call    ??0?$CMap@PEBGPEAU_SUEX_SPACE_OBJECT@@@@QEAA@P6AXPEBG@ZP6AXPEAU_SUEX_SPACE_OBJECT@@@Z@Z; CMap<ushort const *,_SUEX_SPACE_OBJECT *>::CMap<ushort const *,_SUEX_SPACE_OBJECT *>(void (*)(ushort const *),void (*)(_SUEX_SPACE_OBJECT *))
0x1800d1457  nop
0x1800d1458  lea     rdx, [rbp+2C0h+var_2F0]
0x1800d145c  mov     rcx, r15
0x1800d145f  call    ?Begin@?$CMapBase@U_SP_ID@@PEAU_SU_DRIVE_OBJECT@@@@QEAA?AV?$CMapIter@U_SP_ID@@PEAU_SU_DRIVE_OBJECT@@@@XZ; CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(void)
0x1800d1464  movups  xmm0, xmmword ptr [rax]
0x1800d1467  movups  xmmword ptr [rbp+2C0h+RestartKey], xmm0
0x1800d146b  movsd   xmm1, qword ptr [rax+10h]
0x1800d1470  movsd   [rbp+2C0h+var_2F8], xmm1
0x1800d1475  cmp     [rbp+2C0h+RestartKey], r13
0x1800d1479  jz      short loc_1800D14D3
0x1800d147b  mov     rax, [rbp+2C0h+RestartKey+8]
0x1800d147f  test    rax, rax
0x1800d1482  jz      short loc_1800D14D3
0x1800d1484  mov     rbx, [rax+8]
0x1800d1488  mov     rax, [rax]
0x1800d148b  mov     qword ptr [rbp+2C0h+var_318], rax
0x1800d148f  lea     rax, [rbp+2C0h+TableContext]
0x1800d1493  mov     [rsp+3C0h+var_3A0], rax; __int64
0x1800d1498  xor     r9d, r9d
0x1800d149b  mov     edx, 92001h
0x1800d14a0  lea     r8d, [r9+3]
0x1800d14a4  lea     rcx, [rbp+2C0h+var_320]; struct _SP_OBJECT_ID *
0x1800d14a8  call    ??$EnumerateAssociatedStorageObjects@U_SUEX_JOB_OBJECT@@@@YAHPEAU_SP_OBJECT_ID@@IW4_SP_CONTROL_TYPE@@PEAU_SUEX_FILTER@@PEAV?$CMap@PEBGPEAU_SUEX_JOB_OBJECT@@@@@Z; EnumerateAssociatedStorageObjects<_SUEX_JOB_OBJECT>(_SP_OBJECT_ID *,uint,_SP_CONTROL_TYPE,_SUEX_FILTER *,CMap<ushort const *,_SUEX_JOB_OBJECT *> *)
0x1800d14ad  test    eax, eax
0x1800d14af  jz      short loc_1800D14BF
0x1800d14b1  add     rsi, rbx
0x1800d14b4  lea     rcx, [rbp+2C0h+RestartKey]; RestartKey
0x1800d14b8  call    ?Next@?$CMapIter@PEBGPEAU_SUEX_SPACE_OBJECT@@@@QEAAAEAV1@XZ; CMapIter<ushort const *,_SUEX_SPACE_OBJECT *>::Next(void)
0x1800d14bd  jmp     short loc_1800D1475
0x1800d14bf  call    cs:__imp_GetLastError
0x1800d14c5  mov     esi, 490h
0x1800d14ca  cmp     eax, esi
0x1800d14cc  jz      short loc_1800D14D8
0x1800d14ce  jmp     loc_1800D1867
0x1800d14d3  test    rsi, rsi
0x1800d14d6  jnz     short loc_1800D14EA
0x1800d14d8  mov     edx, 64h ; 'd'
0x1800d14dd  mov     rcx, rdi
0x1800d14e0  call    ?Update@?$CSpWmiMethod@U_SPACES_VirtualDisk_Repair@@@@IEAAHG@Z; CSpWmiMethod<_SPACES_VirtualDisk_Repair>::Update(ushort)
0x1800d14e5  jmp     loc_1800D1867
0x1800d14ea  mov     ebx, r13d
0x1800d14ed  mov     [rsp+3C0h+var_378], r13d
0x1800d14f2  mov     [rsp+3C0h+var_380], r13d
0x1800d14f7  mov     r14, r13
0x1800d14fa  lea     rdx, [rbp+2C0h+var_2F0]
0x1800d14fe  lea     rcx, [rbp+2C0h+TableContext]
0x1800d1502  call    ?Begin@?$CMapBase@U_SP_ID@@PEAU_SU_DRIVE_OBJECT@@@@QEAA?AV?$CMapIter@U_SP_ID@@PEAU_SU_DRIVE_OBJECT@@@@XZ; CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(void)
0x1800d1507  movups  xmm0, xmmword ptr [rax]
0x1800d150a  movups  xmmword ptr [rbp+2C0h+var_338], xmm0
0x1800d150e  movsd   xmm1, qword ptr [rax+10h]
0x1800d1513  movsd   [rbp+2C0h+var_328], xmm1
0x1800d1518  lea     r12, aCspstoragepool_10; "CSpStoragePool::RemovePhysicalDisk::_Wa"...
0x1800d151f  cmp     [rbp+2C0h+var_338], r13
0x1800d1523  jz      loc_1800D1634
0x1800d1529  mov     rdi, [rbp+2C0h+var_338+8]
0x1800d152d  test    rdi, rdi
0x1800d1530  jz      loc_1800D1634
0x1800d1536  mov     rdi, [rdi+8]
0x1800d153a  cmp     [rdi+48h], r13w
0x1800d153f  jz      short loc_1800D155D
0x1800d1541  movzx   ecx, word ptr [rdi+48h]
0x1800d1545  add     rcx, rdi
0x1800d1548  lea     rdx, aRegeneration; "Regeneration"
0x1800d154f  call    cs:__imp__o__wcsicmp
0x1800d1555  test    eax, eax
0x1800d1557  jnz     loc_1800D1626
0x1800d155d  movups  xmm0, xmmword ptr [rdi+98h]
0x1800d1564  movdqu  [rsp+3C0h+var_370], xmm0
0x1800d156a  movups  xmm1, xmmword ptr [rdi+18h]
0x1800d156e  movdqu  [rbp+2C0h+var_2F0], xmm1
0x1800d1573  lea     rax, [rsp+3C0h+var_370]
0x1800d1578  mov     [rsp+3C0h+var_3A0], rax
0x1800d157d  lea     r9, [rbp+2C0h+var_2F0]
0x1800d1581  mov     r8d, 10h
0x1800d1587  mov     edx, [rdi+3Ch]
0x1800d158a  lea     rcx, [rbp+2C0h+var_240]
0x1800d1591  call    ?SuexCreateId@@YAKQEAGW4SpSubsystemType@@W4SM_OBJECTTYPE@@ZZ; SuexCreateId(ushort * const,SpSubsystemType,SM_OBJECTTYPE,...)
0x1800d1596  mov     ebx, eax
0x1800d1598  test    eax, eax
0x1800d159a  jz      short loc_1800D15F8
0x1800d159c  jg      short loc_1800D15A2
0x1800d159e  mov     ecx, eax
0x1800d15a0  jmp     short loc_1800D15AB
0x1800d15a2  movzx   ecx, ax
0x1800d15a5  or      ecx, 80070000h
0x1800d15ab  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@J@Z; GleToSmpReturnCode(long)
0x1800d15b0  mov     ecx, cs:dword_180397B68
0x1800d15b6  cmp     ecx, 2
0x1800d15b9  jbe     short loc_1800D1626
0x1800d15bb  mov     [rsp+3C0h+var_360], eax
0x1800d15bf  mov     [rsp+3C0h+var_37C], 1CA2h
0x1800d15c7  mov     qword ptr [rsp+3C0h+var_370], r12
0x1800d15cc  lea     rax, [rsp+3C0h+var_360]
0x1800d15d1  mov     [rsp+3C0h+var_390], rax
0x1800d15d6  lea     rax, [rsp+3C0h+var_37C]
0x1800d15db  mov     [rsp+3C0h+var_398], rax
0x1800d15e0  lea     rax, [rsp+3C0h+var_370]
0x1800d15e5  mov     [rsp+3C0h+var_3A0], rax
0x1800d15ea  lea     rdx, qword_18032CB78
0x1800d15f1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800d15f6  jmp     short loc_1800D1626
0x1800d15f8  lea     r8, [rsp+3C0h+Buffer]
0x1800d15fd  lea     rdx, [rbp+2C0h+var_240]
0x1800d1604  mov     rcx, r15
0x1800d1607  call    ?Find@?$CMapBase@PEAGPEAG@@QEAAHPEAGPEAPEAG@Z; CMapBase<ushort *,ushort *>::Find(ushort *,ushort * *)
0x1800d160c  test    eax, eax
0x1800d160e  jz      short loc_1800D1621
0x1800d1610  imul    rax, [rsp+3C0h+Buffer], 64h ; 'd'
0x1800d1616  xor     edx, edx
0x1800d1618  div     rsi
0x1800d161b  mov     [rdi+58h], ax
0x1800d161f  jmp     short loc_1800D1626
0x1800d1621  mov     [rdi+58h], r13w
0x1800d1626  lea     rcx, [rbp+2C0h+var_338]; RestartKey
0x1800d162a  call    ?Next@?$CMapIter@PEBGPEAU_SUEX_SPACE_OBJECT@@@@QEAAAEAV1@XZ; CMapIter<ushort const *,_SUEX_SPACE_OBJECT *>::Next(void)
0x1800d162f  jmp     loc_1800D151F
0x1800d1634  mov     esi, 490h
0x1800d1639  mov     r12d, [rsp+3C0h+var_380]
0x1800d163e  mov     eax, 9
0x1800d1643  cmp     [rbp+2C0h+var_260], r13d
0x1800d1647  jz      loc_1800D1854
0x1800d164d  mov     r15d, r13d
0x1800d1650  mov     dword ptr [rbp+2C0h+var_320], eax
0x1800d1653  lea     rdx, [rbp+2C0h+var_2F0]
0x1800d1657  lea     rcx, [rbp+2C0h+TableContext]
0x1800d165b  call    ?Begin@?$CMapBase@U_SP_ID@@PEAU_SU_DRIVE_OBJECT@@@@QEAA?AV?$CMapIter@U_SP_ID@@PEAU_SU_DRIVE_OBJECT@@@@XZ; CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(void)
0x1800d1660  movups  xmm0, xmmword ptr [rax]
0x1800d1663  movups  xmmword ptr [rbp+2C0h+var_338], xmm0
0x1800d1667  movsd   xmm1, qword ptr [rax+10h]
0x1800d166c  movsd   [rbp+2C0h+var_328], xmm1
0x1800d1671  xor     ecx, ecx
0x1800d1673  cmp     [rbp+2C0h+var_338], rcx
0x1800d1677  jz      loc_1800D17D4
0x1800d167d  mov     rdi, [rbp+2C0h+var_338+8]
0x1800d1681  test    rdi, rdi
0x1800d1684  jz      loc_1800D17D4
0x1800d168a  mov     rdi, [rdi+8]
0x1800d168e  cmp     [rdi+48h], cx
0x1800d1692  jz      short loc_1800D16B2
0x1800d1694  movzx   ecx, word ptr [rdi+48h]
0x1800d1698  add     rcx, rdi
0x1800d169b  lea     rdx, aRegeneration; "Regeneration"
0x1800d16a2  call    cs:__imp__o__wcsicmp
0x1800d16a8  xor     ecx, ecx
0x1800d16aa  test    eax, eax
0x1800d16ac  jnz     loc_1800D17C8
0x1800d16b2  mov     eax, [rdi+38h]
0x1800d16b5  add     rax, rdi
0x1800d16b8  mov     qword ptr [rbp+2C0h+var_318], rax
0x1800d16bc  lea     r9, [rsp+3C0h+hMem]
0x1800d16c1  mov     r8d, 3
0x1800d16c7  lea     rcx, [rbp+2C0h+var_320]; struct _SP_OBJECT_ID *
0x1800d16cb  call    ??$GetStorageObject@U_SUEX_JOB_OBJECT@@@@YAHPEAU_SP_OBJECT_ID@@IW4_SP_CONTROL_TYPE@@PEAPEAU_SUEX_JOB_OBJECT@@@Z; GetStorageObject<_SUEX_JOB_OBJECT>(_SP_OBJECT_ID *,uint,_SP_CONTROL_TYPE,_SUEX_JOB_OBJECT * *)
0x1800d16d0  test    eax, eax
0x1800d16d2  jnz     loc_1800D1786
0x1800d16d8  lea     r15d, [rax+1]
0x1800d16dc  mov     r14d, [rdi+38h]
0x1800d16e0  add     r14, rdi
0x1800d16e3  movzx   r12d, word ptr [rdi+58h]
0x1800d16e8  call    cs:__imp_GetLastError
0x1800d16ee  cmp     eax, esi
0x1800d16f0  jz      loc_1800D17BA
0x1800d16f6  call    cs:__imp_GetLastError
0x1800d16fc  mov     ebx, eax
0x1800d16fe  test    eax, eax
0x1800d1700  mov     eax, cs:dword_180397B68
0x1800d1706  jnz     short loc_1800D1722
0x1800d1708  cmp     eax, 4
0x1800d170b  jbe     loc_1800D17BA
0x1800d1711  mov     [rsp+3C0h+var_380], 0
0x1800d1719  lea     rdx, dword_18032CADC
0x1800d1720  jmp     short loc_1800D174D
0x1800d1722  cmp     ebx, 7Ah ; 'z'
0x1800d1725  jnz     short loc_1800D173D
0x1800d1727  cmp     eax, 3
0x1800d172a  jbe     loc_1800D17BA
0x1800d1730  mov     [rsp+3C0h+var_380], ebx
0x1800d1734  lea     rdx, byte_18032A93B
0x1800d173b  jmp     short loc_1800D174D
0x1800d173d  cmp     eax, 2
0x1800d1740  jbe     short loc_1800D17BA
0x1800d1742  mov     [rsp+3C0h+var_380], ebx
0x1800d1746  lea     rdx, byte_1803285BD
0x1800d174d  lea     rax, aCspstoragepool_10; "CSpStoragePool::RemovePhysicalDisk::_Wa"...
0x1800d1754  mov     qword ptr [rsp+3C0h+var_370], rax
0x1800d1759  lea     rax, [rsp+3C0h+var_380]
0x1800d175e  mov     [rsp+3C0h+var_390], rax
0x1800d1763  lea     rax, [rsp+3C0h+var_37C]
0x1800d1768  mov     [rsp+3C0h+var_398], rax
0x1800d176d  lea     rax, [rsp+3C0h+var_370]
0x1800d1772  mov     [rsp+3C0h+var_37C], 1CD7h
0x1800d177a  mov     [rsp+3C0h+var_3A0], rax
0x1800d177f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800d1784  jmp     short loc_1800D17BA
0x1800d1786  mov     rcx, [rsp+3C0h+hMem]; hMem
0x1800d178b  movzx   edx, word ptr [rcx+58h]
0x1800d178f  movzx   eax, word ptr [rdi+58h]
0x1800d1793  imul    edx, eax
0x1800d1796  mov     eax, 51EB851Fh
0x1800d179b  imul    edx
0x1800d179d  sar     edx, 5
0x1800d17a0  mov     eax, edx
0x1800d17a2  shr     eax, 1Fh
0x1800d17a5  add     edx, eax
0x1800d17a7  add     r13w, dx
0x1800d17ab  call    cs:__imp_LocalFree
0x1800d17b1  mov     [rsp+3C0h+hMem], 0
0x1800d17ba  lea     rcx, [rbp+2C0h+var_338]; RestartKey
0x1800d17be  call    ?Next@?$CMapIter@PEBGPEAU_SUEX_SPACE_OBJECT@@@@QEAAAEAV1@XZ; CMapIter<ushort const *,_SUEX_SPACE_OBJECT *>::Next(void)
0x1800d17c3  jmp     loc_1800D1671
0x1800d17c8  mov     r14d, [rdi+38h]
0x1800d17cc  add     r14, rdi
0x1800d17cf  mov     r12d, ecx
0x1800d17d2  jmp     short loc_1800D17D9
0x1800d17d4  test    r15d, r15d
0x1800d17d7  jz      short loc_1800D1815
0x1800d17d9  mov     edi, [rsp+3C0h+var_378]
0x1800d17dd  add     di, r12w
0x1800d17e1  mov     [rsp+3C0h+var_378], edi
0x1800d17e5  mov     [rsp+3C0h+Buffer], r14
0x1800d17ea  mov     [rsp+3C0h+var_348], rcx
0x1800d17ef  lea     rdx, [rsp+3C0h+Buffer]; Buffer
0x1800d17f4  lea     rcx, [rbp+2C0h+Table]; Table
0x1800d17f8  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800d17fe  test    al, al
0x1800d1800  jz      short loc_1800D1805
0x1800d1802  dec     [rbp+2C0h+var_260]
0x1800d1805  neg     al
0x1800d1807  sbb     ecx, ecx
0x1800d1809  not     ecx
0x1800d180b  and     ecx, esi; dwErrCode
0x1800d180d  call    cs:__imp_SetLastError
0x1800d1813  jmp     short loc_1800D1819
0x1800d1815  mov     edi, [rsp+3C0h+var_378]
0x1800d1819  lea     eax, [rdi+r13]
0x1800d181d  movzx   eax, ax
0x1800d1820  imul    ecx, eax, 5Bh ; '['
0x1800d1823  mov     eax, 51EB851Fh
0x1800d1828  imul    ecx
0x1800d182a  sar     edx, 5
0x1800d182d  mov     eax, edx
0x1800d182f  shr     eax, 1Fh
0x1800d1832  add     edx, eax
0x1800d1834  add     dx, 9
0x1800d1838  mov     rcx, [rbp+2C0h+var_340]
0x1800d183c  call    ?Update@?$CSpWmiMethod@U_SPACES_VirtualDisk_Repair@@@@IEAAHG@Z; CSpWmiMethod<_SPACES_VirtualDisk_Repair>::Update(ushort)
0x1800d1841  mov     ecx, 1388h; dwMilliseconds
0x1800d1846  call    cs:__imp_Sleep
0x1800d184c  xor     r13d, r13d
0x1800d184f  jmp     loc_1800D163E
0x1800d1854  test    ebx, ebx
0x1800d1856  jz      short loc_1800D1860
0x1800d1858  mov     ecx, ebx; dwErrCode
0x1800d185a  call    cs:__imp_SetLastError
0x1800d1860  lea     r14, aCspstoragepool_10; "CSpStoragePool::RemovePhysicalDisk::_Wa"...
0x1800d1867  mov     eax, cs:dword_180397B68
0x1800d186d  cmp     eax, 5
0x1800d1870  jbe     short loc_1800D189E
  ... truncated ...
```
