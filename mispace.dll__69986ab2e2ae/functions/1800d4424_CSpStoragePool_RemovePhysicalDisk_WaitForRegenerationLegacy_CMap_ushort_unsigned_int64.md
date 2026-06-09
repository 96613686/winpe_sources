# CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy(CMap<ushort *,unsigned __int64> *)

- ea: `0x1800d4424`
- end: `0x1800d4992`
- name: `?_WaitForRegenerationLegacy@RemovePhysicalDisk@CSpStoragePool@@AEAAXPEAV?$CMap@PEAG_K@@@Z`
- size: `1390`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x1800d1388`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x180006350`
- `0x18001fa04`
- `0x180023e3c`
- `0x18002caf0`
- `0x180048ea8`
- `0x180052f74`
- `0x18006156c`
- `0x180062744`
- `0x1800698e0`
- `0x180077258`
- `0x1800954f4`
- `0x1800d4424`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d45d9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d4732`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d45d9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d4732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d477e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d477e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4792`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d48bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d4914`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d48bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d4914`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d484d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d484d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800d48fa`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800d48fa`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800d48a0`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800d48a0`

## string_xrefs

- `0x1800d4464`: `CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy`
- `0x1800d45a2`: `CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy`
- `0x1800d47ef`: `CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy`
- `0x1800d4920`: `CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy(
        const char *a1,
        __int64 a2,
        int a3,
        int a4)
{
  __int16 v6; // r13
  unsigned __int64 v7; // rsi
  __int64 v8; // rax
  __int64 v9; // rbx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  DWORD LastError; // ebx
  __int64 v14; // r14
  __int64 v15; // rax
  __int64 v16; // rdi
  int Id; // eax
  __int64 v18; // rcx
  int v19; // eax
  int v20; // r8d
  int v21; // r9d
  __int16 v22; // r12
  int v23; // r15d
  __int64 v24; // rax
  __int64 v25; // rdi
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  __int16 *v29; // rdx
  int v30; // edi
  BOOLEAN v31; // al
  __int64 v32; // rdx
  int v34; // [rsp+40h] [rbp-C0h] BYREF
  int v35; // [rsp+44h] [rbp-BCh] BYREF
  int v36; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v37; // [rsp+50h] [rbp-B0h] BYREF
  int v38; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h]
  _QWORD Buffer[2]; // [rsp+70h] [rbp-90h] BYREF
  const char *v41; // [rsp+80h] [rbp-80h] BYREF
  PVOID v42[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v43; // [rsp+98h] [rbp-68h]
  __int64 v44; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v45; // [rsp+A8h] [rbp-58h]
  PVOID RestartKey[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v47; // [rsp+C8h] [rbp-38h]
  _OWORD v48[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE TableContext[8]; // [rsp+F0h] [rbp-10h] BYREF
  struct _RTL_AVL_TABLE Table; // [rsp+F8h] [rbp-8h] BYREF
  int v51; // [rsp+160h] [rbp+60h]
  _BYTE v52[512]; // [rsp+180h] [rbp+80h] BYREF

  v41 = a1;
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v36 = 7260;
    Buffer[0] = "CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)word_18032F64A,
      a3,
      a4,
      (__int64)Buffer,
      (__int64)&v36);
  }
  v6 = 0;
  hMem = 0;
  v7 = 0;
  Buffer[0] = 0;
  v44 = 16;
  v45 = 0;
  v47 = 0;
  *(_OWORD *)RestartKey = 0;
  v43 = 0;
  *(_OWORD *)v42 = 0;
  CMap<unsigned short const *,_SUEX_SPACE_OBJECT *>::CMap<unsigned short const *,_SUEX_SPACE_OBJECT *>(TableContext);
  v8 = CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(a2, v48);
  *(_OWORD *)RestartKey = *(_OWORD *)v8;
  v47 = *(_QWORD *)(v8 + 16);
  while ( RestartKey[0] && RestartKey[1] )
  {
    v9 = *((_QWORD *)RestartKey[1] + 1);
    *(_QWORD *)&v45 = *(_QWORD *)RestartKey[1];
    if ( !(unsigned int)EnumerateAssociatedStorageObjects<_SUEX_JOB_OBJECT>(
                          (struct _SP_OBJECT_ID *)&v44,
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
  v36 = 0;
  v34 = 0;
  v14 = 0;
  v15 = CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(TableContext, v48);
  *(_OWORD *)v42 = *(_OWORD *)v15;
  v43 = *(_QWORD *)(v15 + 16);
  while ( v42[0] && v42[1] )
  {
    v16 = *((_QWORD *)v42[1] + 1);
    if ( !*(_WORD *)(v16 + 72) || !(unsigned int)_o__wcsicmp(v16 + *(unsigned __int16 *)(v16 + 72), L"Regeneration") )
    {
      v37 = *(_OWORD *)(v16 + 152);
      v48[0] = *(_OWORD *)(v16 + 24);
      Id = SuexCreateId(v52, *(unsigned int *)(v16 + 60), 16, v48);
      LastError = Id;
      if ( Id )
      {
        if ( Id > 0 )
          v18 = (unsigned __int16)Id | 0x80070000;
        else
          v18 = (unsigned int)Id;
        v19 = GleToSmpReturnCode(v18);
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          v38 = v19;
          v35 = 7330;
          *(_QWORD *)&v37 = "CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            dword_18039EB68,
            (unsigned int)qword_180333AC8,
            v20,
            v21,
            (__int64)&v37,
            (__int64)&v35,
            (__int64)&v38);
        }
      }
      else if ( (unsigned int)CMapBase<unsigned short *,unsigned short *>::Find(a2, v52, Buffer) )
      {
        *(_WORD *)(v16 + 88) = 100LL * Buffer[0] / v7;
      }
      else
      {
        *(_WORD *)(v16 + 88) = 0;
      }
    }
    CMapIter<unsigned short const *,_SUEX_SPACE_OBJECT *>::Next(v42);
  }
  v22 = v34;
LABEL_28:
  if ( v51 )
  {
    v23 = 0;
    LODWORD(v44) = 9;
    v24 = CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(TableContext, v48);
    *(_OWORD *)v42 = *(_OWORD *)v24;
    v43 = *(_QWORD *)(v24 + 16);
    while ( 1 )
    {
      if ( !v42[0] || !v42[1] )
      {
        if ( !v23 )
        {
          LOWORD(v30) = v36;
          goto LABEL_53;
        }
LABEL_49:
        HIWORD(v30) = HIWORD(v36);
        LOWORD(v30) = v22 + v36;
        v36 = v30;
        Buffer[0] = v14;
        Buffer[1] = 0;
        v31 = RtlDeleteElementGenericTableAvl(&Table, Buffer);
        if ( v31 )
          --v51;
        SetLastError(v31 == 0 ? 0x490 : 0);
LABEL_53:
        v32 = (unsigned int)(91 * (unsigned __int16)(v30 + v6) / 100);
        LOWORD(v32) = v32 + 9;
        CSpWmiMethod<_SPACES_VirtualDisk_Repair>::Update(v41, v32);
        Sleep(0x1388u);
        v6 = 0;
        goto LABEL_28;
      }
      v25 = *((_QWORD *)v42[1] + 1);
      if ( *(_WORD *)(v25 + 72) && (unsigned int)_o__wcsicmp(v25 + *(unsigned __int16 *)(v25 + 72), L"Regeneration") )
      {
        v14 = v25 + *(unsigned int *)(v25 + 56);
        v22 = 0;
        goto LABEL_49;
      }
      *(_QWORD *)&v45 = v25 + *(unsigned int *)(v25 + 56);
      if ( (unsigned int)GetStorageObject<_SUEX_JOB_OBJECT>((struct _SP_OBJECT_ID *)&v44) )
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
            if ( (unsigned int)dword_18039EB68 <= 3 )
              goto LABEL_46;
            v34 = 122;
            v29 = (__int16 *)&dword_180331934;
          }
          else
          {
            if ( (unsigned int)dword_18039EB68 <= 2 )
              goto LABEL_46;
            v34 = LastError;
            v29 = (__int16 *)byte_18032F57B;
          }
        }
        else
        {
          if ( (unsigned int)dword_18039EB68 <= 4 )
            goto LABEL_46;
          v34 = 0;
          v29 = &word_180333AFE;
        }
        *(_QWORD *)&v37 = "CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy";
        v35 = 7383;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v26,
          (_DWORD)v29,
          v27,
          v28,
          (__int64)&v37,
          (__int64)&v35,
          (__int64)&v34);
      }
LABEL_46:
      CMapIter<unsigned short const *,_SUEX_SPACE_OBJECT *>::Next(v42);
    }
  }
  if ( LastError )
    SetLastError(LastError);
LABEL_56:
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v34 = 7414;
    v41 = "CSpStoragePool::RemovePhysicalDisk::_WaitForRegenerationLegacy";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)byte_180332263,
      v11,
      v12,
      (__int64)&v41,
      (__int64)&v34);
  }
  return CMap<unsigned short const *,_SUEX_NODE_OBJECT *>::~CMap<unsigned short const *,_SUEX_NODE_OBJECT *>(TableContext);
}

```

## disassembly

```asm
0x1800d4424  mov     [rsp-8+arg_10], rbx
0x1800d4429  push    rbp
0x1800d442a  push    rsi
0x1800d442b  push    rdi
0x1800d442c  push    r12
0x1800d442e  push    r13
0x1800d4430  push    r14
0x1800d4432  push    r15
0x1800d4434  lea     rbp, [rsp-290h]
0x1800d443c  sub     rsp, 390h
0x1800d4443  mov     rax, cs:__security_cookie
0x1800d444a  xor     rax, rsp
0x1800d444d  mov     [rbp+2C0h+var_40], rax
0x1800d4454  mov     r15, rdx
0x1800d4457  mov     rdi, rcx
0x1800d445a  mov     [rbp+2C0h+var_340], rcx
0x1800d445e  mov     eax, cs:dword_18039EB68
0x1800d4464  lea     r14, aCspstoragepool_10; "CSpStoragePool::RemovePhysicalDisk::_Wa"...
0x1800d446b  cmp     eax, 5
0x1800d446e  jbe     short loc_1800D449D
0x1800d4470  mov     [rsp+3C0h+var_378], 1C5Ch
0x1800d4478  mov     [rsp+3C0h+Buffer], r14
0x1800d447d  lea     rax, [rsp+3C0h+var_378]
0x1800d4482  mov     [rsp+3C0h+var_398], rax
0x1800d4487  lea     rax, [rsp+3C0h+Buffer]
0x1800d448c  mov     [rsp+3C0h+var_3A0], rax
0x1800d4491  lea     rdx, word_18032F64A
0x1800d4498  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800d449d  xor     r13d, r13d
0x1800d44a0  mov     [rsp+3C0h+hMem], r13
0x1800d44a5  mov     esi, r13d
0x1800d44a8  mov     [rsp+3C0h+Buffer], r13
0x1800d44ad  mov     [rbp+2C0h+var_320], 10h
0x1800d44b5  xorps   xmm0, xmm0
0x1800d44b8  movdqu  [rbp+2C0h+var_318], xmm0
0x1800d44bd  mov     [rbp+2C0h+var_2F8], r13
0x1800d44c1  xorps   xmm1, xmm1
0x1800d44c4  movdqu  xmmword ptr [rbp+2C0h+RestartKey], xmm1
0x1800d44c9  mov     [rbp+2C0h+var_328], r13
0x1800d44cd  movdqu  xmmword ptr [rbp+2C0h+var_338], xmm0
0x1800d44d2  lea     rcx, [rbp+2C0h+TableContext]
0x1800d44d6  call    ??0?$CMap@PEBGPEAU_SUEX_SPACE_OBJECT@@@@QEAA@P6AXPEBG@ZP6AXPEAU_SUEX_SPACE_OBJECT@@@Z@Z; CMap<ushort const *,_SUEX_SPACE_OBJECT *>::CMap<ushort const *,_SUEX_SPACE_OBJECT *>(void (*)(ushort const *),void (*)(_SUEX_SPACE_OBJECT *))
0x1800d44db  nop
0x1800d44dc  lea     rdx, [rbp+2C0h+var_2F0]
0x1800d44e0  mov     rcx, r15
0x1800d44e3  call    ?Begin@?$CMapBase@U_SP_ID@@PEAU_SU_DRIVE_OBJECT@@@@QEAA?AV?$CMapIter@U_SP_ID@@PEAU_SU_DRIVE_OBJECT@@@@XZ; CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(void)
0x1800d44e8  movups  xmm0, xmmword ptr [rax]
0x1800d44eb  movups  xmmword ptr [rbp+2C0h+RestartKey], xmm0
0x1800d44ef  movsd   xmm1, qword ptr [rax+10h]
0x1800d44f4  movsd   [rbp+2C0h+var_2F8], xmm1
0x1800d44f9  cmp     [rbp+2C0h+RestartKey], r13
0x1800d44fd  jz      short loc_1800D455D
0x1800d44ff  mov     rax, [rbp+2C0h+RestartKey+8]
0x1800d4503  test    rax, rax
0x1800d4506  jz      short loc_1800D455D
0x1800d4508  mov     rbx, [rax+8]
0x1800d450c  mov     rax, [rax]
0x1800d450f  mov     qword ptr [rbp+2C0h+var_318], rax
0x1800d4513  lea     rax, [rbp+2C0h+TableContext]
0x1800d4517  mov     [rsp+3C0h+var_3A0], rax; __int64
0x1800d451c  xor     r9d, r9d
0x1800d451f  mov     edx, 92001h
0x1800d4524  lea     r8d, [r9+3]
0x1800d4528  lea     rcx, [rbp+2C0h+var_320]; struct _SP_OBJECT_ID *
0x1800d452c  call    ??$EnumerateAssociatedStorageObjects@U_SUEX_JOB_OBJECT@@@@YAHPEAU_SP_OBJECT_ID@@IW4_SP_CONTROL_TYPE@@PEAU_SUEX_FILTER@@PEAV?$CMap@PEBGPEAU_SUEX_JOB_OBJECT@@@@@Z; EnumerateAssociatedStorageObjects<_SUEX_JOB_OBJECT>(_SP_OBJECT_ID *,uint,_SP_CONTROL_TYPE,_SUEX_FILTER *,CMap<ushort const *,_SUEX_JOB_OBJECT *> *)
0x1800d4531  test    eax, eax
0x1800d4533  jz      short loc_1800D4543
0x1800d4535  add     rsi, rbx
0x1800d4538  lea     rcx, [rbp+2C0h+RestartKey]; RestartKey
0x1800d453c  call    ?Next@?$CMapIter@PEBGPEAU_SUEX_SPACE_OBJECT@@@@QEAAAEAV1@XZ; CMapIter<ushort const *,_SUEX_SPACE_OBJECT *>::Next(void)
0x1800d4541  jmp     short loc_1800D44F9
0x1800d4543  call    cs:__imp_GetLastError
0x1800d454a  nop     dword ptr [rax+rax+00h]
0x1800d454f  mov     esi, 490h
0x1800d4554  cmp     eax, esi
0x1800d4556  jz      short loc_1800D4562
0x1800d4558  jmp     loc_1800D4927
0x1800d455d  test    rsi, rsi
0x1800d4560  jnz     short loc_1800D4574
0x1800d4562  mov     edx, 64h ; 'd'
0x1800d4567  mov     rcx, rdi
0x1800d456a  call    ?Update@?$CSpWmiMethod@U_SPACES_VirtualDisk_Repair@@@@IEAAHG@Z; CSpWmiMethod<_SPACES_VirtualDisk_Repair>::Update(ushort)
0x1800d456f  jmp     loc_1800D4927
0x1800d4574  mov     ebx, r13d
0x1800d4577  mov     [rsp+3C0h+var_378], r13d
0x1800d457c  mov     [rsp+3C0h+var_380], r13d
0x1800d4581  mov     r14, r13
0x1800d4584  lea     rdx, [rbp+2C0h+var_2F0]
0x1800d4588  lea     rcx, [rbp+2C0h+TableContext]
0x1800d458c  call    ?Begin@?$CMapBase@U_SP_ID@@PEAU_SU_DRIVE_OBJECT@@@@QEAA?AV?$CMapIter@U_SP_ID@@PEAU_SU_DRIVE_OBJECT@@@@XZ; CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(void)
0x1800d4591  movups  xmm0, xmmword ptr [rax]
0x1800d4594  movups  xmmword ptr [rbp+2C0h+var_338], xmm0
0x1800d4598  movsd   xmm1, qword ptr [rax+10h]
0x1800d459d  movsd   [rbp+2C0h+var_328], xmm1
0x1800d45a2  lea     r12, aCspstoragepool_10; "CSpStoragePool::RemovePhysicalDisk::_Wa"...
0x1800d45a9  cmp     [rbp+2C0h+var_338], r13
0x1800d45ad  jz      loc_1800D46C4
0x1800d45b3  mov     rdi, [rbp+2C0h+var_338+8]
0x1800d45b7  test    rdi, rdi
0x1800d45ba  jz      loc_1800D46C4
0x1800d45c0  mov     rdi, [rdi+8]
0x1800d45c4  cmp     [rdi+48h], r13w
0x1800d45c9  jz      short loc_1800D45ED
0x1800d45cb  movzx   ecx, word ptr [rdi+48h]
0x1800d45cf  add     rcx, rdi
0x1800d45d2  lea     rdx, aRegeneration; "Regeneration"
0x1800d45d9  call    cs:__imp__o__wcsicmp
0x1800d45e0  nop     dword ptr [rax+rax+00h]
0x1800d45e5  test    eax, eax
0x1800d45e7  jnz     loc_1800D46B6
0x1800d45ed  movups  xmm0, xmmword ptr [rdi+98h]
0x1800d45f4  movdqu  [rsp+3C0h+var_370], xmm0
0x1800d45fa  movups  xmm1, xmmword ptr [rdi+18h]
0x1800d45fe  movdqu  [rbp+2C0h+var_2F0], xmm1
0x1800d4603  lea     rax, [rsp+3C0h+var_370]
0x1800d4608  mov     [rsp+3C0h+var_3A0], rax
0x1800d460d  lea     r9, [rbp+2C0h+var_2F0]
0x1800d4611  mov     r8d, 10h
0x1800d4617  mov     edx, [rdi+3Ch]
0x1800d461a  lea     rcx, [rbp+2C0h+var_240]
0x1800d4621  call    ?SuexCreateId@@YAKQEAGW4SpSubsystemType@@W4SM_OBJECTTYPE@@ZZ; SuexCreateId(ushort * const,SpSubsystemType,SM_OBJECTTYPE,...)
0x1800d4626  mov     ebx, eax
0x1800d4628  test    eax, eax
0x1800d462a  jz      short loc_1800D4688
0x1800d462c  jg      short loc_1800D4632
0x1800d462e  mov     ecx, eax
0x1800d4630  jmp     short loc_1800D463B
0x1800d4632  movzx   ecx, ax
0x1800d4635  or      ecx, 80070000h
0x1800d463b  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@J@Z; GleToSmpReturnCode(long)
0x1800d4640  mov     ecx, cs:dword_18039EB68
0x1800d4646  cmp     ecx, 2
0x1800d4649  jbe     short loc_1800D46B6
0x1800d464b  mov     [rsp+3C0h+var_360], eax
0x1800d464f  mov     [rsp+3C0h+var_37C], 1CA2h
0x1800d4657  mov     qword ptr [rsp+3C0h+var_370], r12
0x1800d465c  lea     rax, [rsp+3C0h+var_360]
0x1800d4661  mov     [rsp+3C0h+var_390], rax
0x1800d4666  lea     rax, [rsp+3C0h+var_37C]
0x1800d466b  mov     [rsp+3C0h+var_398], rax
0x1800d4670  lea     rax, [rsp+3C0h+var_370]
0x1800d4675  mov     [rsp+3C0h+var_3A0], rax
0x1800d467a  lea     rdx, qword_180333AC8
0x1800d4681  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800d4686  jmp     short loc_1800D46B6
0x1800d4688  lea     r8, [rsp+3C0h+Buffer]
0x1800d468d  lea     rdx, [rbp+2C0h+var_240]
0x1800d4694  mov     rcx, r15
0x1800d4697  call    ?Find@?$CMapBase@PEAGPEAG@@QEAAHPEAGPEAPEAG@Z; CMapBase<ushort *,ushort *>::Find(ushort *,ushort * *)
0x1800d469c  test    eax, eax
0x1800d469e  jz      short loc_1800D46B1
0x1800d46a0  imul    rax, [rsp+3C0h+Buffer], 64h ; 'd'
0x1800d46a6  xor     edx, edx
0x1800d46a8  div     rsi
0x1800d46ab  mov     [rdi+58h], ax
0x1800d46af  jmp     short loc_1800D46B6
0x1800d46b1  mov     [rdi+58h], r13w
0x1800d46b6  lea     rcx, [rbp+2C0h+var_338]; RestartKey
0x1800d46ba  call    ?Next@?$CMapIter@PEBGPEAU_SUEX_SPACE_OBJECT@@@@QEAAAEAV1@XZ; CMapIter<ushort const *,_SUEX_SPACE_OBJECT *>::Next(void)
0x1800d46bf  jmp     loc_1800D45A9
0x1800d46c4  mov     esi, 490h
0x1800d46c9  mov     r12d, [rsp+3C0h+var_380]
0x1800d46ce  mov     eax, 9
0x1800d46d3  cmp     [rbp+2C0h+var_260], r13d
0x1800d46d7  jz      loc_1800D490E
0x1800d46dd  mov     r15d, r13d
0x1800d46e0  mov     dword ptr [rbp+2C0h+var_320], eax
0x1800d46e3  lea     rdx, [rbp+2C0h+var_2F0]
0x1800d46e7  lea     rcx, [rbp+2C0h+TableContext]
0x1800d46eb  call    ?Begin@?$CMapBase@U_SP_ID@@PEAU_SU_DRIVE_OBJECT@@@@QEAA?AV?$CMapIter@U_SP_ID@@PEAU_SU_DRIVE_OBJECT@@@@XZ; CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(void)
0x1800d46f0  movups  xmm0, xmmword ptr [rax]
0x1800d46f3  movups  xmmword ptr [rbp+2C0h+var_338], xmm0
0x1800d46f7  movsd   xmm1, qword ptr [rax+10h]
0x1800d46fc  movsd   [rbp+2C0h+var_328], xmm1
0x1800d4701  xor     ecx, ecx
0x1800d4703  cmp     [rbp+2C0h+var_338], rcx
0x1800d4707  jz      loc_1800D487C
0x1800d470d  mov     rdi, [rbp+2C0h+var_338+8]
0x1800d4711  test    rdi, rdi
0x1800d4714  jz      loc_1800D487C
0x1800d471a  mov     rdi, [rdi+8]
0x1800d471e  cmp     [rdi+48h], cx
0x1800d4722  jz      short loc_1800D4748
0x1800d4724  movzx   ecx, word ptr [rdi+48h]
0x1800d4728  add     rcx, rdi
0x1800d472b  lea     rdx, aRegeneration; "Regeneration"
0x1800d4732  call    cs:__imp__o__wcsicmp
0x1800d4739  nop     dword ptr [rax+rax+00h]
0x1800d473e  xor     ecx, ecx
0x1800d4740  test    eax, eax
0x1800d4742  jnz     loc_1800D4870
0x1800d4748  mov     eax, [rdi+38h]
0x1800d474b  add     rax, rdi
0x1800d474e  mov     qword ptr [rbp+2C0h+var_318], rax
0x1800d4752  lea     r9, [rsp+3C0h+hMem]
0x1800d4757  mov     r8d, 3
0x1800d475d  lea     rcx, [rbp+2C0h+var_320]; struct _SP_OBJECT_ID *
0x1800d4761  call    ??$GetStorageObject@U_SUEX_JOB_OBJECT@@@@YAHPEAU_SP_OBJECT_ID@@IW4_SP_CONTROL_TYPE@@PEAPEAU_SUEX_JOB_OBJECT@@@Z; GetStorageObject<_SUEX_JOB_OBJECT>(_SP_OBJECT_ID *,uint,_SP_CONTROL_TYPE,_SUEX_JOB_OBJECT * *)
0x1800d4766  test    eax, eax
0x1800d4768  jnz     loc_1800D4828
0x1800d476e  lea     r15d, [rax+1]
0x1800d4772  mov     r14d, [rdi+38h]
0x1800d4776  add     r14, rdi
0x1800d4779  movzx   r12d, word ptr [rdi+58h]
0x1800d477e  call    cs:__imp_GetLastError
0x1800d4785  nop     dword ptr [rax+rax+00h]
0x1800d478a  cmp     eax, esi
0x1800d478c  jz      loc_1800D4862
0x1800d4792  call    cs:__imp_GetLastError
0x1800d4799  nop     dword ptr [rax+rax+00h]
0x1800d479e  mov     ebx, eax
0x1800d47a0  test    eax, eax
0x1800d47a2  mov     eax, cs:dword_18039EB68
0x1800d47a8  jnz     short loc_1800D47C4
0x1800d47aa  cmp     eax, 4
0x1800d47ad  jbe     loc_1800D4862
0x1800d47b3  mov     [rsp+3C0h+var_380], 0
0x1800d47bb  lea     rdx, word_180333AFE
0x1800d47c2  jmp     short loc_1800D47EF
0x1800d47c4  cmp     ebx, 7Ah ; 'z'
0x1800d47c7  jnz     short loc_1800D47DF
0x1800d47c9  cmp     eax, 3
0x1800d47cc  jbe     loc_1800D4862
0x1800d47d2  mov     [rsp+3C0h+var_380], ebx
0x1800d47d6  lea     rdx, dword_180331934
0x1800d47dd  jmp     short loc_1800D47EF
0x1800d47df  cmp     eax, 2
0x1800d47e2  jbe     short loc_1800D4862
0x1800d47e4  mov     [rsp+3C0h+var_380], ebx
0x1800d47e8  lea     rdx, byte_18032F57B
0x1800d47ef  lea     rax, aCspstoragepool_10; "CSpStoragePool::RemovePhysicalDisk::_Wa"...
0x1800d47f6  mov     qword ptr [rsp+3C0h+var_370], rax
0x1800d47fb  lea     rax, [rsp+3C0h+var_380]
0x1800d4800  mov     [rsp+3C0h+var_390], rax
0x1800d4805  lea     rax, [rsp+3C0h+var_37C]
0x1800d480a  mov     [rsp+3C0h+var_398], rax
0x1800d480f  lea     rax, [rsp+3C0h+var_370]
0x1800d4814  mov     [rsp+3C0h+var_37C], 1CD7h
0x1800d481c  mov     [rsp+3C0h+var_3A0], rax
0x1800d4821  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800d4826  jmp     short loc_1800D4862
0x1800d4828  mov     rcx, [rsp+3C0h+hMem]; hMem
0x1800d482d  movzx   edx, word ptr [rcx+58h]
0x1800d4831  movzx   eax, word ptr [rdi+58h]
0x1800d4835  imul    edx, eax
0x1800d4838  mov     eax, 51EB851Fh
0x1800d483d  imul    edx
0x1800d483f  sar     edx, 5
0x1800d4842  mov     eax, edx
0x1800d4844  shr     eax, 1Fh
0x1800d4847  add     edx, eax
0x1800d4849  add     r13w, dx
0x1800d484d  call    cs:__imp_LocalFree
0x1800d4854  nop     dword ptr [rax+rax+00h]
0x1800d4859  mov     [rsp+3C0h+hMem], 0
0x1800d4862  lea     rcx, [rbp+2C0h+var_338]; RestartKey
0x1800d4866  call    ?Next@?$CMapIter@PEBGPEAU_SUEX_SPACE_OBJECT@@@@QEAAAEAV1@XZ; CMapIter<ushort const *,_SUEX_SPACE_OBJECT *>::Next(void)
0x1800d486b  jmp     loc_1800D4701
0x1800d4870  mov     r14d, [rdi+38h]
0x1800d4874  add     r14, rdi
0x1800d4877  mov     r12d, ecx
0x1800d487a  jmp     short loc_1800D4881
0x1800d487c  test    r15d, r15d
0x1800d487f  jz      short loc_1800D48C9
0x1800d4881  mov     edi, [rsp+3C0h+var_378]
0x1800d4885  add     di, r12w
0x1800d4889  mov     [rsp+3C0h+var_378], edi
0x1800d488d  mov     [rsp+3C0h+Buffer], r14
0x1800d4892  mov     [rsp+3C0h+var_348], rcx
0x1800d4897  lea     rdx, [rsp+3C0h+Buffer]; Buffer
0x1800d489c  lea     rcx, [rbp+2C0h+Table]; Table
0x1800d48a0  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800d48a7  nop     dword ptr [rax+rax+00h]
0x1800d48ac  test    al, al
0x1800d48ae  jz      short loc_1800D48B3
0x1800d48b0  dec     [rbp+2C0h+var_260]
0x1800d48b3  neg     al
0x1800d48b5  sbb     ecx, ecx
0x1800d48b7  not     ecx
0x1800d48b9  and     ecx, esi; dwErrCode
0x1800d48bb  call    cs:__imp_SetLastError
0x1800d48c2  nop     dword ptr [rax+rax+00h]
0x1800d48c7  jmp     short loc_1800D48CD
0x1800d48c9  mov     edi, [rsp+3C0h+var_378]
0x1800d48cd  lea     eax, [rdi+r13]
0x1800d48d1  movzx   eax, ax
0x1800d48d4  imul    ecx, eax, 5Bh ; '['
0x1800d48d7  mov     eax, 51EB851Fh
0x1800d48dc  imul    ecx
0x1800d48de  sar     edx, 5
0x1800d48e1  mov     eax, edx
0x1800d48e3  shr     eax, 1Fh
0x1800d48e6  add     edx, eax
0x1800d48e8  add     dx, 9
0x1800d48ec  mov     rcx, [rbp+2C0h+var_340]
0x1800d48f0  call    ?Update@?$CSpWmiMethod@U_SPACES_VirtualDisk_Repair@@@@IEAAHG@Z; CSpWmiMethod<_SPACES_VirtualDisk_Repair>::Update(ushort)
0x1800d48f5  mov     ecx, 1388h; dwMilliseconds
0x1800d48fa  call    cs:__imp_Sleep
0x1800d4901  nop     dword ptr [rax+rax+00h]
0x1800d4906  xor     r13d, r13d
  ... truncated ...
```
