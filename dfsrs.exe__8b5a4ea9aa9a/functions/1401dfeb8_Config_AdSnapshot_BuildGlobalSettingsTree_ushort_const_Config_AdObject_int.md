# Config::AdSnapshot::BuildGlobalSettingsTree(ushort const *,Config::AdObject * *,int &)

- ea: `0x1401dfeb8`
- end: `0x1401e0560`
- name: `?BuildGlobalSettingsTree@AdSnapshot@Config@@AEAAPEAVFrsStatus@@PEBGPEAPEAVAdObject@2@AEAH@Z`
- size: `1704`
- prototype: `struct FrsStatus *__fastcall(Config::AdSnapshot *__hidden this, const unsigned __int16 *, struct Config::AdObject **, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1401eeaa0`

## callees

- `0x14000cd1c`
- `0x140019358`
- `0x14001c030`
- `0x14002179c`
- `0x140046a44`
- `0x1401b9494`
- `0x1401dfcec`
- `0x1401dfeb8`
- `0x1401e1884`
- `0x1401e4584`
- `0x1401e470c`
- `0x1401e6a3c`
- `0x1401e7458`
- `0x1401e8830`
- `0x1401e8aa4`
- `0x1401f2444`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401dff7b`
- `KERNEL32!GetCurrentThreadId` at `0x1401e0003`
- `KERNEL32!GetCurrentThreadId` at `0x1401e008b`
- `KERNEL32!GetCurrentThreadId` at `0x1401e012f`
- `KERNEL32!GetCurrentThreadId` at `0x1401e01f5`
- `KERNEL32!GetCurrentThreadId` at `0x1401e0306`
- `KERNEL32!GetCurrentThreadId` at `0x1401e03bd`
- `KERNEL32!GetCurrentThreadId` at `0x1401e0490`
- `KERNEL32!GetCurrentThreadId` at `0x1401e04fe`
- `KERNEL32!GetCurrentThreadId` at `0x1401dff7b`
- `KERNEL32!GetCurrentThreadId` at `0x1401e0003`
- `KERNEL32!GetCurrentThreadId` at `0x1401e008b`
- `KERNEL32!GetCurrentThreadId` at `0x1401e012f`
- `KERNEL32!GetCurrentThreadId` at `0x1401e01f5`
- `KERNEL32!GetCurrentThreadId` at `0x1401e0306`
- `KERNEL32!GetCurrentThreadId` at `0x1401e03bd`
- `KERNEL32!GetCurrentThreadId` at `0x1401e0490`
- `KERNEL32!GetCurrentThreadId` at `0x1401e04fe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1401dfefa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1401dfefa`

## string_xrefs

- `0x1401e03dd`: `Config::AdSnapshot::BuildGlobalSettingsTree`
- `0x1401e0527`: `Config::AdSnapshot::BuildGlobalSettingsTree`
- `0x1401dff43`: `Config::AdSnapshot::BuildGlobalSettingsTree`
- `0x1401dffcb`: `Config::AdSnapshot::BuildGlobalSettingsTree`
- `0x1401e0053`: `Config::AdSnapshot::BuildGlobalSettingsTree`
- `0x1401e00fb`: `Config::AdSnapshot::BuildGlobalSettingsTree`
- `0x1401e01c1`: `Config::AdSnapshot::BuildGlobalSettingsTree`
- `0x1401e02c5`: `Config::AdSnapshot::BuildGlobalSettingsTree`
- `0x1401e036f`: `Config::AdSnapshot::BuildGlobalSettingsTree`
- `0x1401e0427`: `Config::AdSnapshot::BuildGlobalSettingsTree`
- `0x1401e04c6`: `Config::AdSnapshot::BuildGlobalSettingsTree`

## pseudocode

```c
struct FrsStatus *__fastcall Config::AdSnapshot::BuildGlobalSettingsTree(
        Config::AdSnapshot *this,
        const unsigned __int16 *a2,
        struct Config::AdObject **a3,
        int *a4)
{
  __int64 v6; // rbx
  const unsigned __int16 *ParentDn; // rax
  const unsigned __int16 *v8; // r12
  __int64 v9; // rcx
  const unsigned __int16 *v10; // rax
  const unsigned __int16 *v11; // r14
  const unsigned __int16 *v12; // rax
  unsigned int v13; // r8d
  const unsigned __int16 *v14; // rsi
  unsigned int v15; // r8d
  Config::AdObjectList **v16; // rdi
  struct FrsStatus *GlobalSettings; // rsi
  __int64 v18; // r9
  __int64 v19; // r8
  __int64 v20; // rdx
  struct Config::AdObject *v21; // rsi
  __int64 v22; // rcx
  Config::AdStrAttr *Attr; // r14
  struct FrsStatus *v24; // r14
  DWORD v25; // eax
  __int64 v26; // rcx
  struct FrsStatus *v28; // r14
  DWORD v29; // eax
  __int64 v30; // rcx
  int v31; // [rsp+38h] [rbp-39h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-31h]
  struct FrsStatus *v33; // [rsp+48h] [rbp-29h]
  struct Config::AdObject *v34; // [rsp+58h] [rbp-19h] BYREF
  const unsigned __int16 *v35; // [rsp+60h] [rbp-11h] BYREF
  const unsigned __int16 *v36; // [rsp+68h] [rbp-9h] BYREF
  struct Config::AdObject *Value; // [rsp+70h] [rbp-1h] BYREF
  const wchar_t *v38; // [rsp+78h] [rbp+7h] BYREF
  int v39; // [rsp+80h] [rbp+Fh]
  int v40; // [rsp+84h] [rbp+13h]
  const wchar_t *v41; // [rsp+88h] [rbp+17h]
  const unsigned __int16 *v42; // [rsp+E0h] [rbp+6Fh] BYREF
  struct Config::AdObject **v43; // [rsp+E8h] [rbp+77h]
  int *v44; // [rsp+F0h] [rbp+7Fh]

  v44 = a4;
  v43 = a3;
  v42 = a2;
  v6 = 0;
  if ( (unsigned int)_o__wcsnicmp(a2, L"cn=", 3) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v39 = 6156;
      v38 = L"Config::AdSnapshot::BuildGlobalSettingsTree";
      v40 = 4;
      v41 = L"CFAD";
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v38, L"Bad memberDn:%ws", &v42);
    }
    v33 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v31 = 6157;
    goto LABEL_65;
  }
  v35 = a2 + 3;
  ParentDn = Config::AdDn::GetParentDn(a2 + 3, L"cn=");
  v36 = ParentDn;
  v8 = ParentDn;
  if ( !ParentDn )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v39 = 6165;
      v38 = L"Config::AdSnapshot::BuildGlobalSettingsTree";
      v40 = 4;
      v41 = L"CFAD";
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v38, L"Bad memberDnAddr:%ws", &v35);
    }
    v33 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v31 = 6166;
LABEL_65:
    v20 = 13;
    v19 = 0;
    v18 = 1;
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v9,
                                 v20,
                                 v19,
                                 v18,
                                 "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                 "Config::AdSnapshot::BuildGlobalSettingsTree",
                                 v31,
                                 CurrentThreadId,
                                 v33);
  }
  v10 = Config::AdDn::GetParentDn(ParentDn, L"cn=");
  v35 = v10;
  v11 = v10;
  if ( !v10 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v39 = 6174;
      v38 = L"Config::AdSnapshot::BuildGlobalSettingsTree";
      v40 = 4;
      v41 = L"CFAD";
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v38, L"Bad topologyDnAddr:%ws", &v36);
    }
    v33 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v31 = 6175;
    goto LABEL_65;
  }
  v12 = Config::AdDn::GetParentDn(v10, L"cn=");
  Value = (struct Config::AdObject *)v12;
  v14 = v12;
  if ( !v12 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v39 = 6183;
      v38 = L"Config::AdSnapshot::BuildGlobalSettingsTree";
      v40 = 4;
      v41 = L"CFAD";
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v38, L"Bad replicaDnAddrDn:%ws", &v35);
    }
    v33 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v31 = 6184;
    goto LABEL_65;
  }
  v34 = Config::AdObjectList::FindByDn((Config::AdSnapshot *)((char *)this + 40), v12, v13);
  v16 = (Config::AdObjectList **)v34;
  if ( !v34 )
  {
    GlobalSettings = Config::AdSnapshot::GetGlobalSettings(this, v14, &v34);
    if ( GlobalSettings )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v39 = 6204;
        v38 = L"Config::AdSnapshot::BuildGlobalSettingsTree";
        v40 = 2;
        v41 = L"CFAD";
        dbgobj::DbgPrint<unsigned short,unsigned short const *>(
          &v38,
          L"Failed to GetGlobalSettings(). settingsDnAddr:%ws",
          &Value);
      }
      v33 = GlobalSettings;
      CurrentThreadId = GetCurrentThreadId();
      v31 = 6206;
LABEL_27:
      v18 = *(unsigned int *)GlobalSettings;
      v19 = *((unsigned int *)GlobalSettings + 2);
      v20 = *((unsigned int *)GlobalSettings + 1);
      return (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v9,
                                   v20,
                                   v19,
                                   v18,
                                   "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                   "Config::AdSnapshot::BuildGlobalSettingsTree",
                                   v31,
                                   CurrentThreadId,
                                   v33);
    }
    v16 = (Config::AdObjectList **)v34;
    Value = v34;
    std::vector<ReplicaSetManager *>::push_back((char *)this + 48, &Value);
  }
  v34 = Config::AdObjectList::FindByDn(v16[10], v11, v15);
  v21 = v34;
  if ( !v34 )
  {
    GlobalSettings = Config::AdSnapshot::GetReplicaSet(this, v11, (struct Config::AdObject *)v16, &v34);
    if ( GlobalSettings )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v39 = 6223;
        v38 = L"Config::AdSnapshot::BuildGlobalSettingsTree";
        v40 = 2;
        v41 = L"CFAD";
        dbgobj::DbgPrint<unsigned short,unsigned short const *>(
          &v38,
          L"Failed to GetReplicaSet(). replicaDnAddr:%ws",
          &v35);
      }
      v33 = GlobalSettings;
      CurrentThreadId = GetCurrentThreadId();
      v31 = 6226;
      goto LABEL_27;
    }
    v21 = v34;
    v22 = (__int64)v16[10] + 8;
    Value = v34;
    std::vector<ReplicaSetManager *>::push_back(v22, &Value);
  }
  Attr = Config::AdAttrList::FindAttr(v21, L"msDFSR-ReplicationGroupType");
  if ( !Config::AdStrAttr::GetValue(Attr)
    || (unsigned int)Config::AdStrAttr::GetInt32(Attr) != 2
    && (unsigned int)Config::AdStrAttr::GetInt32(Attr) != 3
    && (unsigned int)Config::AdStrAttr::GetInt32(Attr) != 1
    && (unsigned int)Config::AdStrAttr::GetInt32(Attr) )
  {
    *((_BYTE *)v21 + 89) |= 1u;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v39 = 6249;
      v38 = L"Config::AdSnapshot::BuildGlobalSettingsTree";
      v41 = L"CFAD";
      v40 = 2;
      Value = (struct Config::AdObject *)Config::AdStrAttr::GetValue(*((Config::AdStrAttr **)v21 + 5));
      v36 = Config::AdStrAttr::GetValue(Attr);
      dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
        &v38,
        L"Invalid replica set type:%ws replicaDn:%ws",
        &v36,
        &Value);
    }
    *v44 = 0;
    Config::AdSnapshot::ReportInvalidDataEvent(this, v21, L"msDFSR-ReplicationGroupType");
    v33 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v31 = 6256;
    goto LABEL_65;
  }
  *v44 = 1;
  v24 = Config::AdSnapshot::BuildContentSubTree(this, v21);
  if ( v24 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v39 = 6266;
      v38 = L"Config::AdSnapshot::BuildGlobalSettingsTree";
      v41 = L"CFAD";
      v40 = 2;
      Value = (struct Config::AdObject *)Config::AdStrAttr::GetValue(*((Config::AdStrAttr **)v21 + 5));
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(
        &v38,
        L"Failed to BuildContentSubTree(). replicaDn:%ws",
        &Value);
    }
    v25 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v26,
                                 *((unsigned int *)v24 + 1),
                                 *((unsigned int *)v24 + 2),
                                 *(unsigned int *)v24,
                                 "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                 "Config::AdSnapshot::BuildGlobalSettingsTree",
                                 6267,
                                 v25,
                                 v24);
  }
  else
  {
    v28 = Config::AdSnapshot::BuildTopologySubTree(this, v21, v8, a2, v43);
    if ( v28 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v39 = 6275;
        v38 = L"Config::AdSnapshot::BuildGlobalSettingsTree";
        v41 = L"CFAD";
        v40 = 2;
        Value = (struct Config::AdObject *)Config::AdStrAttr::GetValue(*((Config::AdStrAttr **)v21 + 5));
        dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short const *,unsigned short const *>(
          (unsigned int)&v38,
          (unsigned int)L"Failed to BuildTopologySubTree(). replicaDn:%ws memberDn:%ws topologyDn:%ws",
          (unsigned int)&Value,
          (unsigned int)&v42,
          (__int64)&v36);
      }
      v29 = GetCurrentThreadId();
      return (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v30,
                                   *((unsigned int *)v28 + 1),
                                   *((unsigned int *)v28 + 2),
                                   *(unsigned int *)v28,
                                   "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                   "Config::AdSnapshot::BuildGlobalSettingsTree",
                                   6281,
                                   v29,
                                   v28);
    }
    return (struct FrsStatus *)v6;
  }
}

```

## disassembly

```asm
0x1401dfeb8  mov     rax, rsp
0x1401dfebb  mov     [rax+8], rbx
0x1401dfebf  mov     [rax+20h], r9
0x1401dfec3  mov     [rax+18h], r8
0x1401dfec7  mov     [rax+10h], rdx
0x1401dfecb  push    rbp
0x1401dfecc  push    rsi
0x1401dfecd  push    rdi
0x1401dfece  push    r12
0x1401dfed0  push    r13
0x1401dfed2  push    r14
0x1401dfed4  push    r15
0x1401dfed6  lea     rbp, [rax-5Fh]
0x1401dfeda  sub     rsp, 90h
0x1401dfee1  mov     r13, rdx
0x1401dfee4  lea     rdi, aCn_1; "cn="
0x1401dfeeb  mov     r15, rcx
0x1401dfeee  mov     rdx, rdi
0x1401dfef1  mov     rcx, r13
0x1401dfef4  mov     r8d, 3
0x1401dfefa  call    cs:__imp__o__wcsnicmp
0x1401dff01  nop     dword ptr [rax+rax+00h]
0x1401dff06  xor     ebx, ebx
0x1401dff08  test    eax, eax
0x1401dff0a  jnz     loc_1401E04AF
0x1401dff10  lea     rcx, [r13+6]; unsigned __int16 *
0x1401dff14  mov     rdx, rdi; unsigned __int16 *
0x1401dff17  mov     [rbp+57h+var_68], rcx
0x1401dff1b  call    ?GetParentDn@AdDn@Config@@SAPEBGPEBG0@Z; Config::AdDn::GetParentDn(ushort const *,ushort const *)
0x1401dff20  mov     [rbp+57h+var_60], rax
0x1401dff24  mov     r12, rax
0x1401dff27  test    rax, rax
0x1401dff2a  jnz     short loc_1401DFF9D
0x1401dff2c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401dff33  test    rax, rax
0x1401dff36  jz      short loc_1401DFF7B
0x1401dff38  cmp     [rax+40h], ebx
0x1401dff3b  jz      short loc_1401DFF7B
0x1401dff3d  cmp     dword ptr [rax+38h], 4
0x1401dff41  jl      short loc_1401DFF7B
0x1401dff43  lea     rax, aConfigAdsnapsh_40; "Config::AdSnapshot::BuildGlobalSettings"...
0x1401dff4a  mov     [rbp+57h+var_48], 1815h
0x1401dff51  mov     [rbp+57h+var_50], rax
0x1401dff55  lea     r8, [rbp+57h+var_68]
0x1401dff59  lea     rax, aCfad; "CFAD"
0x1401dff60  mov     [rbp+57h+var_44], 4
0x1401dff67  lea     rdx, aBadMemberdnadd; "Bad memberDnAddr:%ws"
0x1401dff6e  mov     [rbp+57h+var_40], rax
0x1401dff72  lea     rcx, [rbp+57h+var_50]
0x1401dff76  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401dff7b  call    cs:__imp_GetCurrentThreadId
0x1401dff82  nop     dword ptr [rax+rax+00h]
0x1401dff87  mov     [rsp+40h], rbx
0x1401dff8c  mov     dword ptr [rsp+0C0h+var_88], eax
0x1401dff90  mov     [rsp+0C0h+var_90], 1816h
0x1401dff98  jmp     loc_1401E051B
0x1401dff9d  mov     rdx, rdi; unsigned __int16 *
0x1401dffa0  mov     rcx, r12; unsigned __int16 *
0x1401dffa3  call    ?GetParentDn@AdDn@Config@@SAPEBGPEBG0@Z; Config::AdDn::GetParentDn(ushort const *,ushort const *)
0x1401dffa8  mov     [rbp+57h+var_68], rax
0x1401dffac  mov     r14, rax
0x1401dffaf  test    rax, rax
0x1401dffb2  jnz     short loc_1401E0025
0x1401dffb4  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401dffbb  test    rax, rax
0x1401dffbe  jz      short loc_1401E0003
0x1401dffc0  cmp     [rax+40h], ebx
0x1401dffc3  jz      short loc_1401E0003
0x1401dffc5  cmp     dword ptr [rax+38h], 4
0x1401dffc9  jl      short loc_1401E0003
0x1401dffcb  lea     rax, aConfigAdsnapsh_40; "Config::AdSnapshot::BuildGlobalSettings"...
0x1401dffd2  mov     [rbp+57h+var_48], 181Eh
0x1401dffd9  mov     [rbp+57h+var_50], rax
0x1401dffdd  lea     r8, [rbp+57h+var_60]
0x1401dffe1  lea     rax, aCfad; "CFAD"
0x1401dffe8  mov     [rbp+57h+var_44], 4
0x1401dffef  lea     rdx, aBadTopologydna; "Bad topologyDnAddr:%ws"
0x1401dfff6  mov     [rbp+57h+var_40], rax
0x1401dfffa  lea     rcx, [rbp+57h+var_50]
0x1401dfffe  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401e0003  call    cs:__imp_GetCurrentThreadId
0x1401e000a  nop     dword ptr [rax+rax+00h]
0x1401e000f  mov     [rsp+40h], rbx
0x1401e0014  mov     dword ptr [rsp+0C0h+var_88], eax
0x1401e0018  mov     [rsp+0C0h+var_90], 181Fh
0x1401e0020  jmp     loc_1401E051B
0x1401e0025  mov     rdx, rdi; unsigned __int16 *
0x1401e0028  mov     rcx, r14; unsigned __int16 *
0x1401e002b  call    ?GetParentDn@AdDn@Config@@SAPEBGPEBG0@Z; Config::AdDn::GetParentDn(ushort const *,ushort const *)
0x1401e0030  mov     [rbp+57h+var_58], rax
0x1401e0034  mov     rsi, rax
0x1401e0037  test    rax, rax
0x1401e003a  jnz     short loc_1401E00AD
0x1401e003c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401e0043  test    rax, rax
0x1401e0046  jz      short loc_1401E008B
0x1401e0048  cmp     [rax+40h], ebx
0x1401e004b  jz      short loc_1401E008B
0x1401e004d  cmp     dword ptr [rax+38h], 4
0x1401e0051  jl      short loc_1401E008B
0x1401e0053  lea     rax, aConfigAdsnapsh_40; "Config::AdSnapshot::BuildGlobalSettings"...
0x1401e005a  mov     [rbp+57h+var_48], 1827h
0x1401e0061  mov     [rbp+57h+var_50], rax
0x1401e0065  lea     r8, [rbp+57h+var_68]
0x1401e0069  lea     rax, aCfad; "CFAD"
0x1401e0070  mov     [rbp+57h+var_44], 4
0x1401e0077  lea     rdx, aBadReplicadnad; "Bad replicaDnAddrDn:%ws"
0x1401e007e  mov     [rbp+57h+var_40], rax
0x1401e0082  lea     rcx, [rbp+57h+var_50]
0x1401e0086  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401e008b  call    cs:__imp_GetCurrentThreadId
0x1401e0092  nop     dword ptr [rax+rax+00h]
0x1401e0097  mov     [rsp+40h], rbx
0x1401e009c  mov     dword ptr [rsp+0C0h+var_88], eax
0x1401e00a0  mov     [rsp+0C0h+var_90], 1828h
0x1401e00a8  jmp     loc_1401E051B
0x1401e00ad  lea     rcx, [r15+28h]; this
0x1401e00b1  mov     rdx, rsi; unsigned __int16 *
0x1401e00b4  call    ?FindByDn@AdObjectList@Config@@QEBAPEAVAdObject@2@PEBGK@Z; Config::AdObjectList::FindByDn(ushort const *,ulong)
0x1401e00b9  mov     [rbp+57h+var_70], rax
0x1401e00bd  mov     rdi, rax
0x1401e00c0  test    rax, rax
0x1401e00c3  jnz     loc_1401E0170
0x1401e00c9  lea     r8, [rbp+57h+var_70]; struct Config::AdObject **
0x1401e00cd  mov     rdx, rsi; unsigned __int16 *
0x1401e00d0  mov     rcx, r15; this
0x1401e00d3  call    ?GetGlobalSettings@AdSnapshot@Config@@QEAAPEAVFrsStatus@@PEBGPEAPEAVAdObject@2@@Z; Config::AdSnapshot::GetGlobalSettings(ushort const *,Config::AdObject * *)
0x1401e00d8  mov     rsi, rax
0x1401e00db  test    rax, rax
0x1401e00de  jz      short loc_1401E015B
0x1401e00e0  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401e00e7  test    rcx, rcx
0x1401e00ea  jz      short loc_1401E012F
0x1401e00ec  cmp     [rcx+40h], ebx
0x1401e00ef  jz      short loc_1401E012F
0x1401e00f1  mov     edi, 2
0x1401e00f6  cmp     [rcx+38h], edi
0x1401e00f9  jl      short loc_1401E012F
0x1401e00fb  lea     rax, aConfigAdsnapsh_40; "Config::AdSnapshot::BuildGlobalSettings"...
0x1401e0102  mov     [rbp+57h+var_48], 183Ch
0x1401e0109  mov     [rbp+57h+var_50], rax
0x1401e010d  lea     r8, [rbp+57h+var_58]
0x1401e0111  lea     rax, aCfad; "CFAD"
0x1401e0118  mov     [rbp+57h+var_44], edi
0x1401e011b  lea     rdx, aFailedToGetglo; "Failed to GetGlobalSettings(). settings"...
0x1401e0122  mov     [rbp+57h+var_40], rax
0x1401e0126  lea     rcx, [rbp+57h+var_50]
0x1401e012a  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401e012f  call    cs:__imp_GetCurrentThreadId
0x1401e0136  nop     dword ptr [rax+rax+00h]
0x1401e013b  mov     [rsp+40h], rsi
0x1401e0140  mov     dword ptr [rsp+0C0h+var_88], eax
0x1401e0144  mov     [rsp+0C0h+var_90], 183Eh
0x1401e014c  mov     r9d, [rsi]
0x1401e014f  mov     r8d, [rsi+8]
0x1401e0153  mov     edx, [rsi+4]
0x1401e0156  jmp     loc_1401E0527
0x1401e015b  mov     rdi, [rbp+57h+var_70]
0x1401e015f  lea     rcx, [r15+30h]
0x1401e0163  lea     rdx, [rbp+57h+var_58]
0x1401e0167  mov     [rbp+57h+var_58], rdi
0x1401e016b  call    ?push_back@?$vector@PEAVReplicaSetManager@@V?$allocator@PEAVReplicaSetManager@@@std@@@std@@QEAAXAEBQEAVReplicaSetManager@@@Z; std::vector<ReplicaSetManager *>::push_back(ReplicaSetManager * const &)
0x1401e0170  mov     rcx, [rdi+50h]; this
0x1401e0174  mov     rdx, r14; unsigned __int16 *
0x1401e0177  call    ?FindByDn@AdObjectList@Config@@QEBAPEAVAdObject@2@PEBGK@Z; Config::AdObjectList::FindByDn(ushort const *,ulong)
0x1401e017c  mov     [rbp+57h+var_70], rax
0x1401e0180  mov     rsi, rax
0x1401e0183  test    rax, rax
0x1401e0186  jnz     loc_1401E0230
0x1401e018c  lea     r9, [rbp+57h+var_70]; struct Config::AdObject **
0x1401e0190  mov     r8, rdi; struct Config::AdObject *
0x1401e0193  mov     rdx, r14; unsigned __int16 *
0x1401e0196  mov     rcx, r15; this
0x1401e0199  call    ?GetReplicaSet@AdSnapshot@Config@@AEAAPEAVFrsStatus@@PEBGPEAVAdObject@2@PEAPEAV42@@Z; Config::AdSnapshot::GetReplicaSet(ushort const *,Config::AdObject *,Config::AdObject * *)
0x1401e019e  mov     rsi, rax
0x1401e01a1  test    rax, rax
0x1401e01a4  jz      short loc_1401E0217
0x1401e01a6  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401e01ad  test    rcx, rcx
0x1401e01b0  jz      short loc_1401E01F5
0x1401e01b2  cmp     [rcx+40h], ebx
0x1401e01b5  jz      short loc_1401E01F5
0x1401e01b7  mov     edi, 2
0x1401e01bc  cmp     [rcx+38h], edi
0x1401e01bf  jl      short loc_1401E01F5
0x1401e01c1  lea     rax, aConfigAdsnapsh_40; "Config::AdSnapshot::BuildGlobalSettings"...
0x1401e01c8  mov     [rbp+57h+var_48], 184Fh
0x1401e01cf  mov     [rbp+57h+var_50], rax
0x1401e01d3  lea     r8, [rbp+57h+var_68]
0x1401e01d7  lea     rax, aCfad; "CFAD"
0x1401e01de  mov     [rbp+57h+var_44], edi
0x1401e01e1  lea     rdx, aFailedToGetrep; "Failed to GetReplicaSet(). replicaDnAdd"...
0x1401e01e8  mov     [rbp+57h+var_40], rax
0x1401e01ec  lea     rcx, [rbp+57h+var_50]
0x1401e01f0  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401e01f5  call    cs:__imp_GetCurrentThreadId
0x1401e01fc  nop     dword ptr [rax+rax+00h]
0x1401e0201  mov     [rsp+40h], rsi
0x1401e0206  mov     dword ptr [rsp+0C0h+var_88], eax
0x1401e020a  mov     [rsp+0C0h+var_90], 1852h
0x1401e0212  jmp     loc_1401E014C
0x1401e0217  mov     rcx, [rdi+50h]
0x1401e021b  lea     rdx, [rbp+57h+var_58]
0x1401e021f  mov     rsi, [rbp+57h+var_70]
0x1401e0223  add     rcx, 8
0x1401e0227  mov     [rbp+57h+var_58], rsi
0x1401e022b  call    ?push_back@?$vector@PEAVReplicaSetManager@@V?$allocator@PEAVReplicaSetManager@@@std@@@std@@QEAAXAEBQEAVReplicaSetManager@@@Z; std::vector<ReplicaSetManager *>::push_back(ReplicaSetManager * const &)
0x1401e0230  lea     rdx, aMsdfsrReplicat_0; "msDFSR-ReplicationGroupType"
0x1401e0237  mov     rcx, rsi; this
0x1401e023a  call    ?FindAttr@AdAttrList@Config@@QEBAPEAVAdAttr@2@PEBG@Z; Config::AdAttrList::FindAttr(ushort const *)
0x1401e023f  mov     rcx, rax; this
0x1401e0242  mov     r14, rax
0x1401e0245  call    ?GetValue@AdStrAttr@Config@@QEBAPEBGXZ; Config::AdStrAttr::GetValue(void)
0x1401e024a  mov     edi, 2
0x1401e024f  test    rax, rax
0x1401e0252  jz      loc_1401E040D
0x1401e0258  mov     rcx, r14; this
0x1401e025b  call    ?GetInt32@AdStrAttr@Config@@QEBAHXZ; Config::AdStrAttr::GetInt32(void)
0x1401e0260  cmp     eax, edi
0x1401e0262  jz      short loc_1401E028E
0x1401e0264  mov     rcx, r14; this
0x1401e0267  call    ?GetInt32@AdStrAttr@Config@@QEBAHXZ; Config::AdStrAttr::GetInt32(void)
0x1401e026c  cmp     eax, 3
0x1401e026f  jz      short loc_1401E028E
0x1401e0271  mov     rcx, r14; this
0x1401e0274  call    ?GetInt32@AdStrAttr@Config@@QEBAHXZ; Config::AdStrAttr::GetInt32(void)
0x1401e0279  cmp     eax, 1
0x1401e027c  jz      short loc_1401E028E
0x1401e027e  mov     rcx, r14; this
0x1401e0281  call    ?GetInt32@AdStrAttr@Config@@QEBAHXZ; Config::AdStrAttr::GetInt32(void)
0x1401e0286  test    eax, eax
0x1401e0288  jnz     loc_1401E040D
0x1401e028e  mov     rax, [rbp+57h+arg_18]
0x1401e0292  mov     rdx, rsi; struct Config::AdObject *
0x1401e0295  mov     rcx, r15; this
0x1401e0298  mov     dword ptr [rax], 1
0x1401e029e  call    ?BuildContentSubTree@AdSnapshot@Config@@AEAAPEAVFrsStatus@@PEAVAdObject@2@@Z; Config::AdSnapshot::BuildContentSubTree(Config::AdObject *)
0x1401e02a3  mov     r14, rax
0x1401e02a6  test    rax, rax
0x1401e02a9  jz      loc_1401E0333
0x1401e02af  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401e02b6  test    rcx, rcx
0x1401e02b9  jz      short loc_1401E0306
0x1401e02bb  cmp     [rcx+40h], ebx
0x1401e02be  jz      short loc_1401E0306
0x1401e02c0  cmp     [rcx+38h], edi
0x1401e02c3  jl      short loc_1401E0306
0x1401e02c5  lea     rax, aConfigAdsnapsh_40; "Config::AdSnapshot::BuildGlobalSettings"...
0x1401e02cc  mov     [rbp+57h+var_48], 187Ah
0x1401e02d3  mov     [rbp+57h+var_50], rax
0x1401e02d7  lea     rax, aCfad; "CFAD"
0x1401e02de  mov     [rbp+57h+var_40], rax
0x1401e02e2  mov     [rbp+57h+var_44], edi
0x1401e02e5  mov     rcx, [rsi+28h]; this
0x1401e02e9  call    ?GetValue@AdStrAttr@Config@@QEBAPEBGXZ; Config::AdStrAttr::GetValue(void)
0x1401e02ee  lea     r8, [rbp+57h+var_58]
0x1401e02f2  mov     [rbp+57h+var_58], rax
0x1401e02f6  lea     rdx, aFailedToBuildc; "Failed to BuildContentSubTree(). replic"...
0x1401e02fd  lea     rcx, [rbp+57h+var_50]
0x1401e0301  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401e0306  call    cs:__imp_GetCurrentThreadId
0x1401e030d  nop     dword ptr [rax+rax+00h]
0x1401e0312  mov     r9d, [r14]
0x1401e0315  mov     r8d, [r14+8]
0x1401e0319  mov     edx, [r14+4]
0x1401e031d  mov     [rsp+40h], r14
0x1401e0322  mov     dword ptr [rsp+0C0h+var_88], eax
0x1401e0326  mov     [rsp+0C0h+var_90], 187Bh
0x1401e032e  jmp     loc_1401E0527
0x1401e0333  mov     rax, [rbp+57h+arg_10]
0x1401e0337  mov     r9, r13; unsigned __int16 *
0x1401e033a  mov     r8, r12; unsigned __int16 *
0x1401e033d  mov     [rsp+0C0h+var_A0], rax; struct Config::AdObject **
0x1401e0342  mov     rdx, rsi; struct Config::AdObject *
0x1401e0345  mov     rcx, r15; this
0x1401e0348  call    ?BuildTopologySubTree@AdSnapshot@Config@@AEAAPEAVFrsStatus@@PEAVAdObject@2@PEBG1PEAPEAV42@@Z; Config::AdSnapshot::BuildTopologySubTree(Config::AdObject *,ushort const *,ushort const *,Config::AdObject * *)
0x1401e034d  mov     r14, rax
0x1401e0350  test    rax, rax
0x1401e0353  jz      loc_1401E0405
0x1401e0359  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401e0360  test    rcx, rcx
0x1401e0363  jz      short loc_1401E03BD
0x1401e0365  cmp     [rcx+40h], ebx
0x1401e0368  jz      short loc_1401E03BD
0x1401e036a  cmp     [rcx+38h], edi
0x1401e036d  jl      short loc_1401E03BD
0x1401e036f  lea     rax, aConfigAdsnapsh_40; "Config::AdSnapshot::BuildGlobalSettings"...
0x1401e0376  mov     [rbp+57h+var_48], 1883h
0x1401e037d  mov     [rbp+57h+var_50], rax
0x1401e0381  lea     rax, aCfad; "CFAD"
0x1401e0388  mov     [rbp+57h+var_40], rax
0x1401e038c  mov     [rbp+57h+var_44], edi
0x1401e038f  mov     rcx, [rsi+28h]; this
0x1401e0393  call    ?GetValue@AdStrAttr@Config@@QEBAPEBGXZ; Config::AdStrAttr::GetValue(void)
0x1401e0398  mov     [rbp+57h+var_58], rax
0x1401e039c  lea     r9, [rbp+57h+arg_8]
0x1401e03a0  lea     rax, [rbp+57h+var_60]
0x1401e03a4  lea     r8, [rbp+57h+var_58]
0x1401e03a8  mov     [rsp+0C0h+var_A0], rax
0x1401e03ad  lea     rdx, aFailedToBuildt; "Failed to BuildTopologySubTree(). repli"...
  ... truncated ...
```
