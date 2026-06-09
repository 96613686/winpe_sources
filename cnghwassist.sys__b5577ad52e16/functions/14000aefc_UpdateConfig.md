# UpdateConfig

- ea: `0x14000aefc`
- end: `0x14000afa8`
- name: `UpdateConfig`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x14000ade0`
- `0x14000ae10`

## callees

- `0x140002d00`
- `0x14000aefc`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000af00`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000af00`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000af15`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000af15`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000af8a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000af8a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000af96`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000af96`

## pseudocode

```c
void UpdateConfig()
{
  int v0; // edx
  __int64 v1; // rcx

  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&g_currentConfigLock, 1u);
  v0 = 2;
  g_currentConfig = 0;
  while ( 1 )
  {
    v1 = 4LL * (unsigned int)--v0;
    if ( CngChatPowerConfig[v1 + 2] )
    {
      if ( LOBYTE(CngChatPowerConfig[v1 + 3]) )
        break;
    }
    if ( !v0 )
      goto LABEL_7;
  }
  g_currentConfig = CngChatPowerConfig[v1];
LABEL_7:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice);
  ExReleaseResourceLite(&g_currentConfigLock);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14000aefc  sub     rsp, 28h
0x14000af00  call    cs:__imp_KeEnterCriticalRegion
0x14000af07  nop     dword ptr [rax+rax+00h]
0x14000af0c  mov     dl, 1; Wait
0x14000af0e  lea     rcx, g_currentConfigLock; Resource
0x14000af15  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000af1c  nop     dword ptr [rax+rax+00h]
0x14000af21  mov     edx, 2
0x14000af26  mov     cs:g_currentConfig, 0
0x14000af30  dec     edx
0x14000af32  lea     r8, CngChatPowerConfig
0x14000af39  mov     ecx, edx
0x14000af3b  shl     rcx, 5
0x14000af3f  cmp     qword ptr [rcx+r8+10h], 0
0x14000af45  jz      short loc_14000AF50
0x14000af47  mov     al, [rcx+r8+18h]
0x14000af4c  test    al, al
0x14000af4e  jnz     short loc_14000AF56
0x14000af50  test    edx, edx
0x14000af52  jnz     short loc_14000AF30
0x14000af54  jmp     short loc_14000AF60
0x14000af56  mov     eax, [rcx+r8]
0x14000af5a  mov     cs:g_currentConfig, eax
0x14000af60  mov     rcx, cs:WPP_GLOBAL_Control
0x14000af67  lea     rax, WPP_GLOBAL_Control
0x14000af6e  cmp     rcx, rax
0x14000af71  jz      short loc_14000AF83
0x14000af73  mov     eax, [rcx+2Ch]
0x14000af76  test    al, 1
0x14000af78  jz      short loc_14000AF83
0x14000af7a  mov     rcx, [rcx+18h]
0x14000af7e  call    WPP_SF_d
0x14000af83  lea     rcx, g_currentConfigLock; Resource
0x14000af8a  call    cs:__imp_ExReleaseResourceLite
0x14000af91  nop     dword ptr [rax+rax+00h]
0x14000af96  call    cs:__imp_KeLeaveCriticalRegion
0x14000af9d  nop     dword ptr [rax+rax+00h]
0x14000afa2  add     rsp, 28h
0x14000afa6  retn
```
