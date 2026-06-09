# CFveApi::UnbindDataVolume(void)

- ea: `0x1800d0898`
- end: `0x1800d0dc1`
- name: `?UnbindDataVolume@CFveApi@@QEAAJXZ`
- size: `1321`
- prototype: `__int64 __fastcall(CFveApi *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006bda0`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180018b10`
- `0x18001b260`
- `0x18001b490`
- `0x18001de20`
- `0x18001eaf4`
- `0x18001f010`
- `0x18001f154`
- `0x180022360`
- `0x18004fa04`
- `0x180058cdc`
- `0x18006e528`
- `0x18007e218`
- `0x1800d0124`
- `0x1800d0898`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800d0d67`
- `ntdll!RtlFreeUnicodeString` at `0x18012853a`
- `ntdll!RtlFreeUnicodeString` at `0x1800d0d67`
- `ntdll!RtlFreeUnicodeString` at `0x18012853a`
- `ntdll!RtlStringFromGUID` at `0x1800d0cd7`
- `ntdll!RtlStringFromGUID` at `0x1800d0cd7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800d0cff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800d0cff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0d56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180128529`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0d56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180128529`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d0cb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d0cb8`

## pseudocode

```c
__int64 __fastcall CFveApi::UnbindDataVolume(CFveApi *this)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  __int64 v4; // r12
  int BootVolume; // ebx
  unsigned int v6; // ebx
  int Next; // ecx
  __int64 v8; // rax
  __int16 v9; // r15
  int v10; // eax
  struct CFveApi *v11; // r15
  int v12; // eax
  int DatumPointer; // eax
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // rcx
  LSTATUS v18; // eax
  bool v19; // cc
  NTSTATUS v20; // eax
  bool v22; // [rsp+34h] [rbp-94h] BYREF
  unsigned int v23; // [rsp+38h] [rbp-90h] BYREF
  struct CFveApi *v24; // [rsp+40h] [rbp-88h] BYREF
  __int64 v25; // [rsp+48h] [rbp-80h] BYREF
  __int64 v26; // [rsp+50h] [rbp-78h] BYREF
  __int64 v27; // [rsp+58h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-68h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+68h] [rbp-60h] BYREF
  GUID Guid; // [rsp+78h] [rbp-50h] BYREF

  GuidString = 0;
  Guid = 0;
  v22 = 0;
  hKey = 0;
  v2 = 0;
  v27 = 0;
  v24 = 0;
  v3 = 0;
  v26 = 0;
  v4 = 0;
  v25 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_82fbf6316f983a090a97009b222379cf_Traceguids);
  BootVolume = CFveApiBase::CheckInited(this);
  if ( BootVolume < 0 )
    goto LABEL_69;
  BootVolume = (*(__int64 (**)(void))(*(_QWORD *)this + 64LL))();
  if ( BootVolume < 0 )
    goto LABEL_69;
  if ( (*(unsigned __int8 (__fastcall **)(CFveApi *))(*(_QWORD *)this + 56LL))(this) )
  {
    BootVolume = -2144272359;
    goto LABEL_69;
  }
  BootVolume = CFveApiBase::VerifyBindDataVolume(this, 1, &v22, &Guid);
  if ( BootVolume < 0 )
    goto LABEL_69;
  if ( !v22 )
  {
    BootVolume = 1;
    goto LABEL_69;
  }
  v6 = 0;
  v23 = 0;
  while ( 1 )
  {
    Next = FveDatasetGetNext(*((_QWORD *)this + 146), 2, 8, v6, (__int64)&v23);
    if ( Next < 0 )
      break;
    v6 = v23;
    Next = FveDatasetGetDatumPointer(*((_QWORD *)this + 146), v23, &v27);
    if ( Next < 0 )
      goto LABEL_14;
    v2 = v27;
    if ( (*(_WORD *)(v27 + 34) & 0xFF00) == 0x200 )
    {
      v8 = *(_QWORD *)(v27 + 8) - *(_QWORD *)&Guid.Data1;
      if ( !v8 )
        v8 = *(_QWORD *)(v27 + 16) - *(_QWORD *)Guid.Data4;
      if ( !v8 )
        break;
    }
    v2 = 0;
    v27 = 0;
  }
  if ( !v2 )
    Next = -1073741275;
  if ( Next < 0 )
    goto LABEL_14;
  v9 = *(_WORD *)(v2 + 32) & 0xF00;
  if ( v9 == 512 )
  {
    BootVolume = CFveApi::GetBootVolume(*((_DWORD *)this + 91), 1, &v24);
    if ( BootVolume < 0 )
      goto LABEL_69;
  }
  v10 = CFveApiBase::RemoveDEVolumeFromDEManagement(this);
  if ( v10 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      WPP_82fbf6316f983a090a97009b222379cf_Traceguids,
      (unsigned int)v10);
  BootVolume = CFveApiBase::DeviceIoctl(this, 0x4556D0ABu);
  if ( (int)(BootVolume + 0x80000000) >= 0 && BootVolume != -2144272361 )
    goto LABEL_69;
  if ( v9 != 512 || !v24 || !*((_QWORD *)v24 + 146) )
    goto LABEL_60;
  v23 = 0;
  while ( 1 )
  {
    v11 = v24;
    v12 = FveDatasetGetNext(*((_QWORD *)v24 + 146), 6, 9, v23, (__int64)&v23);
    if ( v12 < 0 )
      break;
    DatumPointer = FveDatasetGetDatumPointer(*((_QWORD *)v11 + 146), v23, &v26);
    if ( DatumPointer < 0 )
      goto LABEL_37;
    v3 = v26;
    v14 = *(_QWORD *)(v2 + 8) - *(_QWORD *)(v26 + 8);
    if ( !v14 )
      v14 = *(_QWORD *)(v2 + 16) - *(_QWORD *)(v26 + 16);
    if ( v14 )
      goto LABEL_41;
    if ( v4 )
    {
      FveDatumFree(v4);
      v25 = 0;
    }
    v12 = FveDatumNestedExtractFirst(v3, 25, 23, &v25);
    if ( v12 >= 0 )
    {
      v4 = v25;
      v16 = *((_QWORD *)this + 146);
      v17 = *(_QWORD *)(v16 + 16) - *(_QWORD *)(v25 + 8);
      if ( !v17 )
        v17 = *(_QWORD *)(v16 + 24) - *(_QWORD *)(v25 + 16);
      if ( !v17 )
        break;
LABEL_41:
      v3 = 0;
      v26 = 0;
    }
    else
    {
      v15 = 0;
      if ( v12 != -1073741275 )
        v15 = v12;
      if ( v15 < 0 )
      {
        BootVolume = FromNtStatus(v15);
        v4 = v25;
        goto LABEL_69;
      }
      v3 = 0;
      v26 = 0;
      v4 = v25;
    }
  }
  Next = 0;
  if ( v12 != -1073741275 )
    Next = v12;
  if ( Next < 0 )
  {
LABEL_14:
    BootVolume = FromNtStatus(Next);
    goto LABEL_69;
  }
  if ( !v3 )
    goto LABEL_60;
  DatumPointer = FveDatasetEraseDatum(*((_QWORD *)v11 + 146), v23);
  if ( DatumPointer < 0 || (DatumPointer = FveDatasetCompress(*((_QWORD *)v11 + 146)), DatumPointer < 0) )
  {
LABEL_37:
    Next = DatumPointer;
    goto LABEL_14;
  }
  BootVolume = CFveApiBase::CommitChangesHelper((__int64)v24, 0, 0, 0);
  if ( BootVolume >= 0 )
  {
LABEL_60:
    if ( BootVolume < 0 )
    {
      BootVolume = 0;
      v18 = RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\FveAutoUnlock",
              0,
              0x2000000u,
              &hKey);
      if ( v18 != 2 )
      {
        v19 = v18 <= 0;
        if ( v18 )
          goto LABEL_66;
        v20 = RtlStringFromGUID(&Guid, &GuidString);
        if ( v20 < 0 )
        {
          BootVolume = v20 | 0x10000000;
          goto LABEL_69;
        }
        v18 = RegDeleteKeyExW(hKey, GuidString.Buffer, 0, 0);
        v19 = v18 <= 0;
        if ( v18 )
        {
LABEL_66:
          if ( v19 )
            BootVolume = v18;
          else
            BootVolume = (unsigned __int16)v18 | 0x80070000;
        }
      }
    }
  }
LABEL_69:
  if ( v24 )
    (*(void (__fastcall **)(struct CFveApi *))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v4 )
    FveDatumFree(v4);
  if ( hKey )
    RegCloseKey(hKey);
  RtlFreeUnicodeString(&GuidString);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      94,
      WPP_82fbf6316f983a090a97009b222379cf_Traceguids,
      (unsigned int)BootVolume);
  return (unsigned int)BootVolume;
}

```

## disassembly

```asm
0x1800d0898  mov     r11, rsp
0x1800d089b  push    rbx
0x1800d089c  push    rsi
0x1800d089d  push    rdi
0x1800d089e  push    r12
0x1800d08a0  push    r14
0x1800d08a2  push    r15
0x1800d08a4  sub     rsp, 98h
0x1800d08ab  mov     rax, cs:__security_cookie
0x1800d08b2  xor     rax, rsp
0x1800d08b5  mov     [rsp+0C8h+var_40], rax
0x1800d08bd  mov     r14, rcx
0x1800d08c0  xorps   xmm0, xmm0
0x1800d08c3  movups  xmmword ptr [rsp+0C8h+GuidString.Length], xmm0
0x1800d08c8  xorps   xmm1, xmm1
0x1800d08cb  movups  xmmword ptr [rsp+0C8h+Guid.Data1], xmm1
0x1800d08d0  mov     [rsp+0C8h+var_94], 0
0x1800d08d5  mov     qword ptr [r11-68h], 0
0x1800d08dd  xor     esi, esi
0x1800d08df  mov     [r11-70h], rsi
0x1800d08e3  mov     [rsp+0C8h+var_88], rsi
0x1800d08e8  xor     edi, edi
0x1800d08ea  mov     [r11-78h], rdi
0x1800d08ee  xor     r12d, r12d
0x1800d08f1  mov     [r11-80h], r12
0x1800d08f5  lea     r15, WPP_GLOBAL_Control
0x1800d08fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0903  cmp     rcx, r15
0x1800d0906  jz      short loc_1800D0922
0x1800d0908  test    byte ptr [rcx+1Ch], 20h
0x1800d090c  jz      short loc_1800D0922
0x1800d090e  lea     edx, [rsi+5Ch]
0x1800d0911  lea     r8, WPP_82fbf6316f983a090a97009b222379cf_Traceguids
0x1800d0918  mov     rcx, [rcx+10h]
0x1800d091c  call    WPP_SF_
0x1800d0921  nop
0x1800d0922  mov     rcx, r14; this
0x1800d0925  call    ?CheckInited@CFveApiBase@@QEBAJXZ; CFveApiBase::CheckInited(void)
0x1800d092a  mov     ebx, eax
0x1800d092c  mov     [rsp+0C8h+var_98], eax
0x1800d0930  test    eax, eax
0x1800d0932  js      loc_1800D0D29
0x1800d0938  mov     rax, [r14]
0x1800d093b  mov     rax, [rax+40h]
0x1800d093f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0944  mov     ebx, eax
0x1800d0946  mov     [rsp+0C8h+var_98], eax
0x1800d094a  test    eax, eax
0x1800d094c  js      loc_1800D0D29
0x1800d0952  mov     rax, [r14]
0x1800d0955  mov     rcx, r14
0x1800d0958  mov     rax, [rax+38h]
0x1800d095c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0961  test    al, al
0x1800d0963  jz      short loc_1800D096C
0x1800d0965  mov     ebx, 80310019h
0x1800d096a  jmp     short loc_1800D099A
0x1800d096c  lea     r9, [rsp+0C8h+Guid]; struct _GUID *
0x1800d0971  lea     r8, [rsp+0C8h+var_94]; bool *
0x1800d0976  mov     dl, 1; bool
0x1800d0978  mov     rcx, r14; this
0x1800d097b  call    ?VerifyBindDataVolume@CFveApiBase@@QEAAJ_NPEA_NPEAU_GUID@@@Z; CFveApiBase::VerifyBindDataVolume(bool,bool *,_GUID *)
0x1800d0980  mov     ebx, eax
0x1800d0982  mov     [rsp+0C8h+var_98], eax
0x1800d0986  test    eax, eax
0x1800d0988  js      loc_1800D0D29
0x1800d098e  cmp     [rsp+0C8h+var_94], 0
0x1800d0993  jnz     short loc_1800D09A3
0x1800d0995  mov     ebx, 1
0x1800d099a  mov     [rsp+0C8h+var_98], ebx
0x1800d099e  jmp     loc_1800D0D29
0x1800d09a3  xor     ebx, ebx
0x1800d09a5  mov     [rsp+0C8h+var_90], ebx
0x1800d09a9  mov     r15d, 200h
0x1800d09af  mov     edx, 2
0x1800d09b4  lea     r8d, [rdx+6]
0x1800d09b8  lea     rax, [rsp+0C8h+var_90]
0x1800d09bd  mov     [rsp+0C8h+phkResult], rax
0x1800d09c2  mov     r9d, ebx
0x1800d09c5  mov     rcx, [r14+490h]
0x1800d09cc  call    FveDatasetGetNext
0x1800d09d1  mov     ecx, eax
0x1800d09d3  test    eax, eax
0x1800d09d5  js      short loc_1800D0A43
0x1800d09d7  lea     r8, [rsp+0C8h+var_70]
0x1800d09dc  mov     ebx, [rsp+0C8h+var_90]
0x1800d09e0  mov     edx, ebx
0x1800d09e2  mov     rcx, [r14+490h]
0x1800d09e9  call    FveDatasetGetDatumPointer
0x1800d09ee  mov     ecx, eax; int
0x1800d09f0  test    eax, eax
0x1800d09f2  jns     short loc_1800D0A04
0x1800d09f4  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800d09f9  mov     ebx, eax
0x1800d09fb  mov     [rsp+0C8h+var_98], eax
0x1800d09ff  jmp     loc_1800D0D22
0x1800d0a04  mov     rsi, [rsp+0C8h+var_70]
0x1800d0a09  movzx   eax, word ptr [rsi+22h]
0x1800d0a0d  mov     edx, 0FF00h
0x1800d0a12  and     ax, dx
0x1800d0a15  cmp     ax, r15w
0x1800d0a19  jnz     short loc_1800D0A37
0x1800d0a1b  mov     rax, [rsi+8]
0x1800d0a1f  sub     rax, qword ptr [rsp+0C8h+Guid.Data1]
0x1800d0a24  jnz     short loc_1800D0A32
0x1800d0a26  mov     rax, [rsi+10h]
0x1800d0a2a  sub     rax, qword ptr [rsp+0C8h+Guid.Data4]
0x1800d0a32  test    rax, rax
0x1800d0a35  jz      short loc_1800D0A43
0x1800d0a37  xor     esi, esi
0x1800d0a39  mov     [rsp+0C8h+var_70], rsi
0x1800d0a3e  jmp     loc_1800D09AF
0x1800d0a43  mov     eax, 0C0000225h
0x1800d0a48  test    rsi, rsi
0x1800d0a4b  cmovz   ecx, eax
0x1800d0a4e  test    ecx, ecx
0x1800d0a50  js      short loc_1800D09F4
0x1800d0a52  mov     r15d, 0F00h
0x1800d0a58  and     r15w, [rsi+20h]
0x1800d0a5d  mov     eax, 200h
0x1800d0a62  cmp     r15w, ax
0x1800d0a66  jnz     short loc_1800D0A89
0x1800d0a68  lea     r8, [rsp+0C8h+var_88]; struct CFveApi **
0x1800d0a6d  mov     dl, 1; bool
0x1800d0a6f  mov     ecx, [r14+16Ch]; unsigned int
0x1800d0a76  call    ?GetBootVolume@CFveApi@@SAJK_NPEAPEAV1@@Z; CFveApi::GetBootVolume(ulong,bool,CFveApi * *)
0x1800d0a7b  mov     ebx, eax
0x1800d0a7d  mov     [rsp+0C8h+var_98], eax
0x1800d0a81  test    eax, eax
0x1800d0a83  js      loc_1800D0D22
0x1800d0a89  mov     rcx, r14; this
0x1800d0a8c  call    ?RemoveDEVolumeFromDEManagement@CFveApiBase@@IEAAJXZ; CFveApiBase::RemoveDEVolumeFromDEManagement(void)
0x1800d0a91  test    eax, eax
0x1800d0a93  jns     short loc_1800D0AC6
0x1800d0a95  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0a9c  lea     rdx, WPP_GLOBAL_Control
0x1800d0aa3  cmp     rcx, rdx
0x1800d0aa6  jz      short loc_1800D0AC6
0x1800d0aa8  test    byte ptr [rcx+1Ch], 2
0x1800d0aac  jz      short loc_1800D0AC6
0x1800d0aae  mov     edx, 5Dh ; ']'
0x1800d0ab3  mov     r9d, eax
0x1800d0ab6  lea     r8, WPP_82fbf6316f983a090a97009b222379cf_Traceguids
0x1800d0abd  mov     rcx, [rcx+10h]
0x1800d0ac1  call    WPP_SF_d
0x1800d0ac6  mov     edx, 4556D0ABh; unsigned int
0x1800d0acb  mov     rcx, r14; this
0x1800d0ace  call    ?DeviceIoctl@CFveApiBase@@IEAAJK@Z; CFveApiBase::DeviceIoctl(ulong)
0x1800d0ad3  mov     ebx, eax
0x1800d0ad5  mov     [rsp+0C8h+var_98], eax
0x1800d0ad9  mov     ecx, 80000000h
0x1800d0ade  add     eax, ecx
0x1800d0ae0  test    ecx, eax
0x1800d0ae2  jnz     short loc_1800D0AF0
0x1800d0ae4  cmp     ebx, 80310017h
0x1800d0aea  jnz     loc_1800D0D22
0x1800d0af0  mov     eax, 200h
0x1800d0af5  cmp     r15w, ax
0x1800d0af9  jnz     loc_1800D0C89
0x1800d0aff  mov     rcx, [rsp+0C8h+var_88]
0x1800d0b04  test    rcx, rcx
0x1800d0b07  jz      loc_1800D0C89
0x1800d0b0d  cmp     qword ptr [rcx+490h], 0
0x1800d0b15  jz      loc_1800D0C89
0x1800d0b1b  mov     [rsp+0C8h+var_90], 0
0x1800d0b23  mov     r15, [rsp+0C8h+var_88]
0x1800d0b28  mov     edx, 6
0x1800d0b2d  lea     r8d, [rdx+3]
0x1800d0b31  lea     rax, [rsp+0C8h+var_90]
0x1800d0b36  mov     [rsp+0C8h+phkResult], rax
0x1800d0b3b  mov     r9d, [rsp+0C8h+var_90]
0x1800d0b40  mov     rcx, [r15+490h]
0x1800d0b47  call    FveDatasetGetNext
0x1800d0b4c  test    eax, eax
0x1800d0b4e  js      loc_1800D0C26
0x1800d0b54  lea     r8, [rsp+0C8h+var_78]
0x1800d0b59  mov     edx, [rsp+0C8h+var_90]
0x1800d0b5d  mov     rcx, [r15+490h]
0x1800d0b64  call    FveDatasetGetDatumPointer
0x1800d0b69  test    eax, eax
0x1800d0b6b  jns     short loc_1800D0B74
0x1800d0b6d  mov     ecx, eax
0x1800d0b6f  jmp     loc_1800D09F4
0x1800d0b74  mov     rdi, [rsp+0C8h+var_78]
0x1800d0b79  mov     rax, [rsi+8]
0x1800d0b7d  sub     rax, [rdi+8]
0x1800d0b81  jnz     short loc_1800D0B8B
0x1800d0b83  mov     rax, [rsi+10h]
0x1800d0b87  sub     rax, [rdi+10h]
0x1800d0b8b  test    rax, rax
0x1800d0b8e  jz      short loc_1800D0B99
0x1800d0b90  xor     edi, edi
0x1800d0b92  mov     [rsp+0C8h+var_78], rdi
0x1800d0b97  jmp     short loc_1800D0B23
0x1800d0b99  test    r12, r12
0x1800d0b9c  jz      short loc_1800D0BAF
0x1800d0b9e  mov     rcx, r12
0x1800d0ba1  call    FveDatumFree
0x1800d0ba6  mov     [rsp+0C8h+var_80], 0
0x1800d0baf  mov     edx, 19h
0x1800d0bb4  lea     r8d, [rdx-2]
0x1800d0bb8  lea     r9, [rsp+0C8h+var_80]
0x1800d0bbd  mov     rcx, rdi
0x1800d0bc0  call    FveDatumNestedExtractFirst
0x1800d0bc5  test    eax, eax
0x1800d0bc7  jns     short loc_1800D0BFD
0x1800d0bc9  xor     ecx, ecx
0x1800d0bcb  cmp     eax, 0C0000225h
0x1800d0bd0  cmovnz  ecx, eax; int
0x1800d0bd3  test    ecx, ecx
0x1800d0bd5  jns     short loc_1800D0BEC
0x1800d0bd7  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800d0bdc  mov     ebx, eax
0x1800d0bde  mov     [rsp+0C8h+var_98], eax
0x1800d0be2  mov     r12, [rsp+0C8h+var_80]
0x1800d0be7  jmp     loc_1800D0D22
0x1800d0bec  xor     edi, edi
0x1800d0bee  mov     [rsp+0C8h+var_78], rdi
0x1800d0bf3  mov     r12, [rsp+0C8h+var_80]
0x1800d0bf8  jmp     loc_1800D0B23
0x1800d0bfd  mov     r12, [rsp+0C8h+var_80]
0x1800d0c02  mov     rdx, [r14+490h]
0x1800d0c09  mov     rcx, [rdx+10h]
0x1800d0c0d  sub     rcx, [r12+8]
0x1800d0c12  jnz     short loc_1800D0C1D
0x1800d0c14  mov     rcx, [rdx+18h]
0x1800d0c18  sub     rcx, [r12+10h]
0x1800d0c1d  test    rcx, rcx
0x1800d0c20  jnz     loc_1800D0B90
0x1800d0c26  xor     ecx, ecx
0x1800d0c28  cmp     eax, 0C0000225h
0x1800d0c2d  cmovnz  ecx, eax
0x1800d0c30  test    ecx, ecx
0x1800d0c32  js      loc_1800D09F4
0x1800d0c38  test    rdi, rdi
0x1800d0c3b  jz      short loc_1800D0C89
0x1800d0c3d  mov     edx, [rsp+0C8h+var_90]
0x1800d0c41  mov     rcx, [r15+490h]
0x1800d0c48  call    FveDatasetEraseDatum
0x1800d0c4d  test    eax, eax
0x1800d0c4f  js      loc_1800D0B6D
0x1800d0c55  mov     rcx, [r15+490h]
0x1800d0c5c  call    FveDatasetCompress
0x1800d0c61  test    eax, eax
0x1800d0c63  js      loc_1800D0B6D
0x1800d0c69  xor     r9d, r9d
0x1800d0c6c  xor     r8d, r8d
0x1800d0c6f  xor     edx, edx
0x1800d0c71  mov     rcx, [rsp+0C8h+var_88]
0x1800d0c76  call    ?CommitChangesHelper@CFveApiBase@@AEAAJ_NW4_FVE_COMMIT_SCENARIO_TYPE@@K@Z; CFveApiBase::CommitChangesHelper(bool,_FVE_COMMIT_SCENARIO_TYPE,ulong)
0x1800d0c7b  mov     ebx, eax
0x1800d0c7d  mov     [rsp+0C8h+var_98], eax
0x1800d0c81  test    eax, eax
0x1800d0c83  js      loc_1800D0D22
0x1800d0c89  test    ebx, ebx
0x1800d0c8b  jns     loc_1800D0D22
0x1800d0c91  xor     ebx, ebx
0x1800d0c93  mov     [rsp+0C8h+var_98], ebx
0x1800d0c97  lea     rax, [rsp+0C8h+hKey]
0x1800d0c9c  mov     [rsp+0C8h+phkResult], rax; phkResult
0x1800d0ca1  mov     r9d, 2000000h; samDesired
0x1800d0ca7  xor     r8d, r8d; ulOptions
0x1800d0caa  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d0cb1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800d0cb8  call    cs:__imp_RegOpenKeyExW
0x1800d0cbf  nop     dword ptr [rax+rax+00h]
0x1800d0cc4  cmp     eax, 2
0x1800d0cc7  jz      short loc_1800D0D1E
0x1800d0cc9  test    eax, eax
0x1800d0ccb  jnz     short loc_1800D0D0F
0x1800d0ccd  lea     rdx, [rsp+0C8h+GuidString]; GuidString
0x1800d0cd2  lea     rcx, [rsp+0C8h+Guid]; Guid
0x1800d0cd7  call    cs:__imp_RtlStringFromGUID
0x1800d0cde  nop     dword ptr [rax+rax+00h]
0x1800d0ce3  test    eax, eax
0x1800d0ce5  jns     short loc_1800D0CEF
0x1800d0ce7  mov     ebx, eax
0x1800d0ce9  bts     ebx, 1Ch
0x1800d0ced  jmp     short loc_1800D0D1E
0x1800d0cef  xor     r9d, r9d; Reserved
0x1800d0cf2  xor     r8d, r8d; samDesired
0x1800d0cf5  mov     rdx, [rsp+0C8h+GuidString.Buffer]; lpSubKey
0x1800d0cfa  mov     rcx, [rsp+0C8h+hKey]; hKey
0x1800d0cff  call    cs:__imp_RegDeleteKeyExW
0x1800d0d06  nop     dword ptr [rax+rax+00h]
0x1800d0d0b  test    eax, eax
0x1800d0d0d  jz      short loc_1800D0D22
0x1800d0d0f  jg      short loc_1800D0D15
0x1800d0d11  mov     ebx, eax
0x1800d0d13  jmp     short loc_1800D0D1E
0x1800d0d15  movzx   ebx, ax
0x1800d0d18  or      ebx, 80070000h
0x1800d0d1e  mov     [rsp+0C8h+var_98], ebx
0x1800d0d22  lea     r15, WPP_GLOBAL_Control
0x1800d0d29  mov     rcx, [rsp+0C8h+var_88]
0x1800d0d2e  test    rcx, rcx
0x1800d0d31  jz      short loc_1800D0D3F
0x1800d0d33  mov     rax, [rcx]
0x1800d0d36  mov     rax, [rax+10h]
0x1800d0d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
