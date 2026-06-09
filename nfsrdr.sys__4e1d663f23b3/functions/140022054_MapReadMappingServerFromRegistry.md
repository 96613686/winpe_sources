# MapReadMappingServerFromRegistry

- ea: `0x140022054`
- end: `0x140022217`
- name: `MapReadMappingServerFromRegistry`
- size: `451`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140022c5c`
- `0x14002d428`

## callees

- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140022054`
- `0x140038550`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140022151`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140022151`

## string_xrefs

- `0x1400220de`: `SOFTWARE\Microsoft\ServicesForNFS`
- `0x14002212f`: `SOFTWARE\Microsoft\ServicesForNFS`

## pseudocode

```c
__int64 __fastcall MapReadMappingServerFromRegistry(__int64 a1)
{
  NTSTATUS Registry; // ebx
  __int64 v4; // [rsp+68h] [rbp+10h] BYREF

  LODWORD(v4) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
  *(_DWORD *)&g_UniMappingServer.Length = 34078720;
  g_UniMappingServer.Buffer = (PWSTR)g_wzMappingServer;
  memset(g_wzMappingServer, 0, sizeof(g_wzMappingServer));
  Registry = NfsReadRegistry(&stru_140041018, L"SOFTWARE\\Microsoft\\ServicesForNFS", (__int64)&v4, 4);
  if ( Registry >= 0 && (_DWORD)v4 )
  {
    *(_DWORD *)(a1 + 2316) |= 0x800u;
    Registry = NfsReadRegistry(
                 &stru_140041018,
                 L"SOFTWARE\\Microsoft\\ServicesForNFS",
                 (__int64)&g_UniMappingServer,
                 16);
    if ( Registry < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
      g_UniMappingServer.Length = 0;
    }
    else
    {
      Registry = RtlDowncaseUnicodeString(&g_UniMappingServer, &g_UniMappingServer, 0);
      if ( Registry < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return (unsigned int)Registry;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return (unsigned int)Registry;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Z(
          WPP_GLOBAL_Control->AttachedDevice,
          66,
          WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids,
          &g_UniMappingServer);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
  return (unsigned int)Registry;
}

```

## disassembly

```asm
0x140022054  push    rbx
0x140022056  push    rbp
0x140022057  push    rsi
0x140022058  push    rdi
0x140022059  sub     rsp, 38h
0x14002205d  mov     rdi, rcx
0x140022060  mov     dword ptr [rsp+58h+arg_8], 0
0x140022068  mov     rcx, cs:WPP_GLOBAL_Control
0x14002206f  lea     rsi, WPP_GLOBAL_Control
0x140022076  lea     rbp, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x14002207d  cmp     rcx, rsi
0x140022080  jz      short loc_14002209A
0x140022082  mov     eax, [rcx+2Ch]
0x140022085  test    al, 10h
0x140022087  jz      short loc_14002209A
0x140022089  mov     rcx, [rcx+18h]
0x14002208d  mov     edx, 40h ; '@'
0x140022092  mov     r8, rbp
0x140022095  call    WPP_SF_
0x14002209a  lea     rcx, g_wzMappingServer; void *
0x1400220a1  mov     dword ptr cs:g_UniMappingServer.Length, 2080000h
0x1400220ab  mov     r8d, 208h; Size
0x1400220b1  mov     cs:g_UniMappingServer.Buffer, rcx
0x1400220b8  xor     edx, edx; Val
0x1400220ba  call    memset
0x1400220bf  lea     rax, [rsp+58h+arg_8]
0x1400220c4  mov     [rsp+58h+var_30], 4; int
0x1400220cc  mov     r9d, 4
0x1400220d2  mov     [rsp+58h+var_38], rax; __int64
0x1400220d7  lea     r8, aMappingserverl; "MappingServerLookup"
0x1400220de  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\ServicesForNFS"
0x1400220e5  lea     rcx, stru_140041018; SourceString
0x1400220ec  call    NfsReadRegistry
0x1400220f1  mov     ebx, eax
0x1400220f3  test    eax, eax
0x1400220f5  js      loc_1400221E4
0x1400220fb  cmp     dword ptr [rsp+58h+arg_8], 0
0x140022100  jz      loc_1400221E4
0x140022106  bts     dword ptr [rdi+90Ch], 0Bh
0x14002210e  lea     r8, aMappingservers; "MappingServers"
0x140022115  lea     rdi, g_UniMappingServer
0x14002211c  mov     [rsp+58h+var_30], 10h; int
0x140022124  mov     r9d, 7
0x14002212a  mov     [rsp+58h+var_38], rdi; __int64
0x14002212f  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\ServicesForNFS"
0x140022136  lea     rcx, stru_140041018; SourceString
0x14002213d  call    NfsReadRegistry
0x140022142  mov     ebx, eax
0x140022144  test    eax, eax
0x140022146  js      short loc_1400221B7
0x140022148  xor     r8d, r8d; AllocateDestinationString
0x14002214b  mov     rdx, rdi; SourceString
0x14002214e  mov     rcx, rdi; DestinationString
0x140022151  call    cs:__imp_RtlDowncaseUnicodeString
0x140022158  nop     dword ptr [rax+rax+00h]
0x14002215d  mov     ebx, eax
0x14002215f  test    eax, eax
0x140022161  jns     short loc_14002218E
0x140022163  mov     rcx, cs:WPP_GLOBAL_Control
0x14002216a  cmp     rcx, rsi
0x14002216d  jz      loc_14002220B
0x140022173  mov     eax, [rcx+2Ch]
0x140022176  test    al, 1
0x140022178  jz      short loc_14002218E
0x14002217a  mov     rcx, [rcx+18h]
0x14002217e  mov     edx, 41h ; 'A'
0x140022183  mov     r9d, ebx
0x140022186  mov     r8, rbp
0x140022189  call    WPP_SF_d
0x14002218e  mov     rcx, cs:WPP_GLOBAL_Control
0x140022195  cmp     rcx, rsi
0x140022198  jz      short loc_14002220B
0x14002219a  mov     eax, [rcx+2Ch]
0x14002219d  test    al, 4
0x14002219f  jz      short loc_1400221E4
0x1400221a1  mov     rcx, [rcx+18h]
0x1400221a5  mov     edx, 42h ; 'B'
0x1400221aa  mov     r9, rdi
0x1400221ad  mov     r8, rbp
0x1400221b0  call    WPP_SF_Z
0x1400221b5  jmp     short loc_1400221E4
0x1400221b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400221be  cmp     rcx, rsi
0x1400221c1  jz      short loc_1400221DB
0x1400221c3  mov     eax, [rcx+2Ch]
0x1400221c6  test    al, 1
0x1400221c8  jz      short loc_1400221DB
0x1400221ca  mov     rcx, [rcx+18h]
0x1400221ce  mov     edx, 43h ; 'C'
0x1400221d3  mov     r8, rbp
0x1400221d6  call    WPP_SF_
0x1400221db  xor     eax, eax
0x1400221dd  mov     cs:g_UniMappingServer.Length, ax
0x1400221e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400221eb  cmp     rcx, rsi
0x1400221ee  jz      short loc_14002220B
0x1400221f0  mov     eax, [rcx+2Ch]
0x1400221f3  test    al, 10h
0x1400221f5  jz      short loc_14002220B
0x1400221f7  mov     rcx, [rcx+18h]
0x1400221fb  mov     edx, 44h ; 'D'
0x140022200  mov     r9d, ebx
0x140022203  mov     r8, rbp
0x140022206  call    WPP_SF_d
0x14002220b  mov     eax, ebx
0x14002220d  add     rsp, 38h
0x140022211  pop     rdi
0x140022212  pop     rsi
0x140022213  pop     rbp
0x140022214  pop     rbx
0x140022215  retn
```
