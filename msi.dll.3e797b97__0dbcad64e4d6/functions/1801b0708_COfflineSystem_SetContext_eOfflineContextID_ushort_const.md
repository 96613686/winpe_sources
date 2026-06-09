# COfflineSystem::SetContext(eOfflineContextID,ushort const *)

- ea: `0x1801b0708`
- end: `0x1801b0a17`
- name: `?SetContext@COfflineSystem@@QEAAKW4eOfflineContextID@@PEBG@Z`
- size: `783`
- prototype: `unsigned int __high(enum eOfflineContextID, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801b0a20`

## callees

- `0x18005a250`
- `0x18006dc80`
- `0x180097608`
- `0x18011a988`
- `0x1801b0124`
- `0x1801b0708`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1801b09e5`
- `ADVAPI32!RegOpenKeyExW` at `0x1801b0894`
- `ADVAPI32!RegOpenKeyExW` at `0x1801b08de`
- `ADVAPI32!RegOpenKeyExW` at `0x1801b0894`
- `ADVAPI32!RegOpenKeyExW` at `0x1801b08de`
- `ADVAPI32!RegOpenKeyExW` at `0x1801b09d7`
- `ADVAPI32!RegCloseKey` at `0x1801b08f7`
- `ADVAPI32!RegCloseKey` at `0x1801b0916`
- `ADVAPI32!RegCloseKey` at `0x1801b0939`
- `ADVAPI32!RegCloseKey` at `0x1801b0961`
- `ADVAPI32!RegCloseKey` at `0x1801b08f7`
- `ADVAPI32!RegCloseKey` at `0x1801b0916`
- `ADVAPI32!RegCloseKey` at `0x1801b0939`
- `ADVAPI32!RegCloseKey` at `0x1801b0961`
- `KERNEL32!LocalAlloc` at `0x1801b07ea`
- `KERNEL32!LocalAlloc` at `0x1801b07ea`

## string_xrefs

- `0x1801b082d`: `\Installer\`

## pseudocode

```c
__int64 __fastcall COfflineSystem::SetContext(HKEY a1, int a2, const WCHAR *a3)
{
  unsigned __int64 v5; // rbx
  unsigned int FileAttributes; // eax
  unsigned __int16 *v7; // rax
  COfflineSystem *v8; // rcx
  unsigned int LogicInstallerPath; // ebx
  int (__high *v11)(const unsigned __int16 *, enum ismEnum, struct IStorage **); // rax
  struct _FILETIME *phkResult; // [rsp+20h] [rbp-10h]
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF
  HKEY v14; // [rsp+68h] [rbp+38h] BYREF

  hKey = a1;
  switch ( a2 )
  {
    case 0:
      COfflineSystem::ReleaseRegistryKeys((COfflineSystem *)&g_OfflineSystem);
      RegOpenKeyAPI = RegOpenKeyExW;
      RegCreateKeyAPI = (int (*)(HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *))RegCreateKeyExW;
      v11 = (int (__high *)(const unsigned __int16 *, enum ismEnum, struct IStorage **))&RealOpenRootStorage;
      goto LABEL_43;
    case 1:
      if ( !g_OfflineSystem || !qword_1803135D0 || !(_DWORD)dword_1803135E8 )
        return 1627;
      RegOpenKeyAPI = (int (*)(HKEY, const unsigned __int16 *, unsigned int, unsigned int, HKEY *))OfflineRegOpenKey;
      RegCreateKeyAPI = (int (*)(HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *))OfflineRegCreateKey;
      v11 = (int (__high *)(const unsigned __int16 *, enum ismEnum, struct IStorage **))&OfflineOpenRootStorage;
LABEL_43:
      OpenRootStorage = v11;
      return 0;
    case 2:
    case 3:
      if ( a3 )
      {
        if ( *a3 )
        {
          hKey = 0;
          if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, &hKey) )
          {
            if ( a2 != 2 )
            {
              if ( qword_1803135D0 )
                RegCloseKey(qword_1803135D0);
              qword_1803135D0 = hKey;
              return 0;
            }
            LogicInstallerPath = COfflineSystem::GetLogicInstallerPath(v8, hKey);
            if ( !LogicInstallerPath )
            {
              v14 = 0;
              if ( !RegOpenKeyExW(hKey, L"Classes", 0, 0x20019u, &v14) )
              {
                if ( g_OfflineSystem )
                  RegCloseKey(g_OfflineSystem);
                g_OfflineSystem = hKey;
                if ( ::hKey )
                  RegCloseKey(::hKey);
                ::hKey = v14;
                return 0;
              }
              LogicInstallerPath = 87;
            }
            RegCloseKey(hKey);
            return LogicInstallerPath;
          }
        }
      }
      return 87;
  }
  if ( a2 != 4 )
    return 87;
  if ( !a3 )
    return 87;
  if ( !*a3 )
    return 87;
  hKey = 0;
  if ( (int)StringCchLengthW(a3, 0x104u, (unsigned __int64 *)&hKey) < 0 )
    return 87;
  v5 = (unsigned __int64)hKey;
  if ( hKey && a3[(_QWORD)hKey - 1] == 92 )
    v5 = (unsigned __int64)hKey - 1;
  if ( v5 - 1 > 0x102 )
    return 87;
  FileAttributes = MsiGetFileAttributesEx(a3, 0, 0, 0, phkResult, 0);
  if ( FileAttributes == -1 || (FileAttributes & 0x10) == 0 )
    return 87;
  v7 = qword_1803135D8;
  if ( !qword_1803135D8 )
  {
    v7 = (unsigned __int16 *)LocalAlloc(0, 0x208u);
    qword_1803135D8 = v7;
    if ( !v7 )
      return 1627;
  }
  LODWORD(dword_1803135E8) = 0;
  if ( (int)StringCchCopyNW(v7, 0x104u, a3, v5) < 0
    || (int)StringCchCopyNW(&qword_1803135D8[v5], 260 - v5, L"\\Installer\\", 0xBu) < 0 )
  {
    return 1627;
  }
  LODWORD(dword_1803135E8) = v5 + 11;
  return 0;
}

```

## disassembly

```asm
0x1801b0708  mov     [rsp-18h+arg_8], rbx
0x1801b070d  mov     [rsp-18h+arg_10], rsi
0x1801b0712  mov     [rsp-18h+hKey], rcx
0x1801b0717  push    rbp
0x1801b0718  push    rdi
0x1801b0719  push    r14
0x1801b071b  mov     rbp, rsp
0x1801b071e  sub     rsp, 30h
0x1801b0722  xor     r14d, r14d
0x1801b0725  mov     rdi, r8
0x1801b0728  mov     ebx, edx
0x1801b072a  mov     ecx, edx
0x1801b072c  test    edx, edx
0x1801b072e  jz      loc_1801B09CB
0x1801b0734  sub     ecx, 1
0x1801b0737  jz      loc_1801B0984
0x1801b073d  sub     ecx, 1
0x1801b0740  jz      loc_1801B085F
0x1801b0746  sub     ecx, 1
0x1801b0749  jz      loc_1801B085F
0x1801b074f  cmp     ecx, 1
0x1801b0752  jnz     loc_1801B097D
0x1801b0758  test    r8, r8
0x1801b075b  jz      loc_1801B097D
0x1801b0761  cmp     [r8], r14w
0x1801b0765  jz      loc_1801B097D
0x1801b076b  mov     esi, 104h
0x1801b0770  mov     [rbp+hKey], r14
0x1801b0774  mov     edx, esi; unsigned __int64
0x1801b0776  lea     r8, [rbp+hKey]; unsigned __int64 *
0x1801b077a  mov     rcx, rdi; unsigned __int16 *
0x1801b077d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1801b0782  test    eax, eax
0x1801b0784  js      loc_1801B097D
0x1801b078a  mov     rbx, [rbp+hKey]
0x1801b078e  test    rbx, rbx
0x1801b0791  jz      short loc_1801B07A1
0x1801b0793  lea     eax, [r14+5Ch]
0x1801b0797  cmp     ax, [rdi+rbx*2-2]
0x1801b079c  jnz     short loc_1801B07A1
0x1801b079e  dec     rbx
0x1801b07a1  lea     rax, [rbx-1]
0x1801b07a5  cmp     rax, 102h
0x1801b07ab  ja      loc_1801B097D
0x1801b07b1  xor     r9d, r9d; struct _FILETIME *
0x1801b07b4  mov     [rsp+30h+var_8], r14; struct _FILETIME *
0x1801b07b9  xor     r8d, r8d; unsigned __int64 *
0x1801b07bc  xor     edx, edx; unsigned int *
0x1801b07be  mov     rcx, rdi; lpFileName
0x1801b07c1  call    ?MsiGetFileAttributesEx@@YAKPEBGPEAKPEA_KPEAU_FILETIME@@33@Z; MsiGetFileAttributesEx(ushort const *,ulong *,unsigned __int64 *,_FILETIME *,_FILETIME *,_FILETIME *)
0x1801b07c6  cmp     eax, 0FFFFFFFFh
0x1801b07c9  jz      loc_1801B097D
0x1801b07cf  test    al, 10h
0x1801b07d1  jz      loc_1801B097D
0x1801b07d7  mov     rax, cs:qword_1803135D8
0x1801b07de  test    rax, rax
0x1801b07e1  jnz     short loc_1801B0806
0x1801b07e3  mov     edx, 208h; uBytes
0x1801b07e8  xor     ecx, ecx; uFlags
0x1801b07ea  call    cs:__imp_LocalAlloc
0x1801b07f1  nop     dword ptr [rax+rax+00h]
0x1801b07f6  mov     cs:qword_1803135D8, rax
0x1801b07fd  test    rax, rax
0x1801b0800  jz      loc_1801B09C4
0x1801b0806  mov     r9, rbx; unsigned __int64
0x1801b0809  mov     cs:dword_1803135E8, r14d
0x1801b0810  mov     r8, rdi; unsigned __int16 *
0x1801b0813  mov     rdx, rsi; unsigned __int64
0x1801b0816  mov     rcx, rax; unsigned __int16 *
0x1801b0819  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1801b081e  test    eax, eax
0x1801b0820  js      loc_1801B09C4
0x1801b0826  mov     rax, cs:qword_1803135D8
0x1801b082d  lea     r8, aInstaller_0; "\\Installer\\"
0x1801b0834  sub     rsi, rbx
0x1801b0837  mov     r9d, 0Bh; unsigned __int64
0x1801b083d  mov     rdx, rsi; unsigned __int64
0x1801b0840  lea     rcx, [rax+rbx*2]; unsigned __int16 *
0x1801b0844  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1801b0849  test    eax, eax
0x1801b084b  js      loc_1801B09C4
0x1801b0851  lea     eax, [rbx+0Bh]
0x1801b0854  mov     cs:dword_1803135E8, eax
0x1801b085a  jmp     loc_1801B0A01
0x1801b085f  test    rdi, rdi
0x1801b0862  jz      loc_1801B097D
0x1801b0868  cmp     [r8], r14w
0x1801b086c  jz      loc_1801B097D
0x1801b0872  lea     rax, [rbp+hKey]
0x1801b0876  mov     [rbp+hKey], r14
0x1801b087a  mov     esi, 20019h
0x1801b087f  mov     [rsp+30h+phkResult], rax; phkResult
0x1801b0884  mov     r9d, esi; samDesired
0x1801b0887  xor     r8d, r8d; ulOptions
0x1801b088a  mov     rdx, rdi; lpSubKey
0x1801b088d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801b0894  call    cs:__imp_RegOpenKeyExW
0x1801b089b  nop     dword ptr [rax+rax+00h]
0x1801b08a0  test    eax, eax
0x1801b08a2  jnz     loc_1801B097D
0x1801b08a8  cmp     ebx, 2
0x1801b08ab  jnz     loc_1801B0955
0x1801b08b1  mov     rdx, [rbp+hKey]; HKEY
0x1801b08b5  call    ?GetLogicInstallerPath@COfflineSystem@@IEAAKPEAUHKEY__@@@Z; COfflineSystem::GetLogicInstallerPath(HKEY__ *)
0x1801b08ba  mov     ebx, eax
0x1801b08bc  test    eax, eax
0x1801b08be  jnz     short loc_1801B08F3
0x1801b08c0  mov     rcx, [rbp+hKey]; hKey
0x1801b08c4  lea     rax, [rbp+arg_18]
0x1801b08c8  mov     r9d, esi; samDesired
0x1801b08cb  mov     [rsp+30h+phkResult], rax; phkResult
0x1801b08d0  xor     r8d, r8d; ulOptions
0x1801b08d3  mov     [rbp+arg_18], r14
0x1801b08d7  lea     rdx, aClasses; "Classes"
0x1801b08de  call    cs:__imp_RegOpenKeyExW
0x1801b08e5  nop     dword ptr [rax+rax+00h]
0x1801b08ea  test    eax, eax
0x1801b08ec  jz      short loc_1801B090A
0x1801b08ee  mov     ebx, 57h ; 'W'
0x1801b08f3  mov     rcx, [rbp+hKey]; hKey
0x1801b08f7  call    cs:__imp_RegCloseKey
0x1801b08fe  nop     dword ptr [rax+rax+00h]
0x1801b0903  mov     eax, ebx
0x1801b0905  jmp     loc_1801B0A03
0x1801b090a  mov     rcx, cs:?g_OfflineSystem@@3VCOfflineSystem@@A; hKey
0x1801b0911  test    rcx, rcx
0x1801b0914  jz      short loc_1801B0922
0x1801b0916  call    cs:__imp_RegCloseKey
0x1801b091d  nop     dword ptr [rax+rax+00h]
0x1801b0922  mov     rcx, cs:hKey; hKey
0x1801b0929  mov     rax, [rbp+hKey]
0x1801b092d  mov     cs:?g_OfflineSystem@@3VCOfflineSystem@@A, rax; COfflineSystem g_OfflineSystem
0x1801b0934  test    rcx, rcx
0x1801b0937  jz      short loc_1801B0945
0x1801b0939  call    cs:__imp_RegCloseKey
0x1801b0940  nop     dword ptr [rax+rax+00h]
0x1801b0945  mov     rax, [rbp+arg_18]
0x1801b0949  mov     cs:hKey, rax
0x1801b0950  jmp     loc_1801B0A01
0x1801b0955  mov     rcx, cs:qword_1803135D0; hKey
0x1801b095c  test    rcx, rcx
0x1801b095f  jz      short loc_1801B096D
0x1801b0961  call    cs:__imp_RegCloseKey
0x1801b0968  nop     dword ptr [rax+rax+00h]
0x1801b096d  mov     rax, [rbp+hKey]
0x1801b0971  mov     cs:qword_1803135D0, rax
0x1801b0978  jmp     loc_1801B0A01
0x1801b097d  mov     eax, 57h ; 'W'
0x1801b0982  jmp     short loc_1801B0A03
0x1801b0984  cmp     cs:?g_OfflineSystem@@3VCOfflineSystem@@A, r14; COfflineSystem g_OfflineSystem
0x1801b098b  jz      short loc_1801B09C4
0x1801b098d  cmp     cs:qword_1803135D0, r14
0x1801b0994  jz      short loc_1801B09C4
0x1801b0996  cmp     cs:dword_1803135E8, r14d
0x1801b099d  jz      short loc_1801B09C4
0x1801b099f  lea     rax, ?OfflineRegOpenKey@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; OfflineRegOpenKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1801b09a6  mov     cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA, rax; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1801b09ad  lea     rax, ?OfflineRegCreateKey@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; OfflineRegCreateKey(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x1801b09b4  mov     cs:?RegCreateKeyAPI@@3P6AJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@ZEA, rax; long (*RegCreateKeyAPI)(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x1801b09bb  lea     rax, ?OfflineOpenRootStorage@@YAJPEBGW4ismEnum@@PEAPEAUIStorage@@@Z; OfflineOpenRootStorage(ushort const *,ismEnum,IStorage * *)
0x1801b09c2  jmp     short loc_1801B09FA
0x1801b09c4  mov     eax, 65Bh
0x1801b09c9  jmp     short loc_1801B0A03
0x1801b09cb  lea     rcx, ?g_OfflineSystem@@3VCOfflineSystem@@A; this
0x1801b09d2  call    ?ReleaseRegistryKeys@COfflineSystem@@IEAAXXZ; COfflineSystem::ReleaseRegistryKeys(void)
0x1801b09d7  mov     rax, cs:__imp_RegOpenKeyExW
0x1801b09de  mov     cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA, rax; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1801b09e5  mov     rax, cs:__imp_RegCreateKeyExW
0x1801b09ec  mov     cs:?RegCreateKeyAPI@@3P6AJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@ZEA, rax; long (*RegCreateKeyAPI)(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x1801b09f3  lea     rax, ?RealOpenRootStorage@@YAJPEBGW4ismEnum@@PEAPEAUIStorage@@@Z; RealOpenRootStorage(ushort const *,ismEnum,IStorage * *)
0x1801b09fa  mov     cs:?OpenRootStorage@@3P6AJPEBGW4ismEnum@@PEAPEAUIStorage@@@ZEA, rax; long (*OpenRootStorage)(ushort const *,ismEnum,IStorage * *)
0x1801b0a01  xor     eax, eax
0x1801b0a03  mov     rbx, [rsp+30h+arg_8]
0x1801b0a08  mov     rsi, [rsp+30h+arg_10]
0x1801b0a0d  add     rsp, 30h
0x1801b0a11  pop     r14
0x1801b0a13  pop     rdi
0x1801b0a14  pop     rbp
0x1801b0a15  retn
```
