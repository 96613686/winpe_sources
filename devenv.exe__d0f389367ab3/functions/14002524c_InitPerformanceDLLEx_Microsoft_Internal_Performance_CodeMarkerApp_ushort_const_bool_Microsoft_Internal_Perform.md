# InitPerformanceDLLEx(Microsoft::Internal::Performance::CodeMarkerApp,ushort const *,bool,Microsoft::Internal::Performance::CodeMarkerEvent,bool)

- ea: `0x14002524c`
- end: `0x1400254a9`
- name: `?InitPerformanceDLLEx@@YAXW4CodeMarkerApp@Performance@Internal@Microsoft@@PEBG_NW4CodeMarkerEvent@234@2@Z`
- size: `605`
- prototype: `void __high(enum Microsoft::Internal::Performance::CodeMarkerApp, const unsigned __int16 *, bool, enum Microsoft::Internal::Performance::CodeMarkerEvent, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140025210`

## callees

- `0x140001020`
- `0x140016200`
- `0x14002524c`
- `0x1400254b0`
- `0x14002d240`
- `0x140067cd0`
- `0x14006b530`
- `0x14006b540`

## import_xrefs

- `KERNEL32!AddAtomW` at `0x14002540f`
- `KERNEL32!AddAtomW` at `0x140025433`
- `KERNEL32!AddAtomW` at `0x14002540f`
- `KERNEL32!AddAtomW` at `0x140025433`
- `KERNEL32!GetFileAttributesW` at `0x1400253b1`
- `KERNEL32!GetFileAttributesW` at `0x1400253b1`
- `KERNEL32!LoadLibraryW` at `0x1400253c5`
- `KERNEL32!LoadLibraryW` at `0x1400253c5`
- `KERNEL32!GetModuleFileNameW` at `0x140025316`
- `KERNEL32!GetModuleFileNameW` at `0x140025316`

## pseudocode

```c
void __fastcall InitPerformanceDLLEx(int a1, unsigned __int16 *a2, __int64 a3, unsigned int a4, char a5)
{
  signed __int64 v8; // rdx
  wchar_t *v9; // rcx
  __int64 v10; // rbx
  wchar_t v11; // ax
  bool v12; // zf
  wchar_t *v13; // rax
  HMODULE LibraryW; // rax
  unsigned int v15; // eax
  unsigned int v16; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Drive[6]; // [rsp+54h] [rbp-ACh] BYREF
  wchar_t Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Dir[256]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR Filename[264]; // [rsp+470h] [rbp+370h] BYREF
  wchar_t Ext[256]; // [rsp+680h] [rbp+580h] BYREF
  wchar_t v22[256]; // [rsp+880h] [rbp+780h] BYREF

  if ( a2 && !ghInstPerf )
  {
    if ( (unsigned __int8)FEnabledInRegistry(a2) )
    {
      v8 = (char *)off_14009D7C0 - (char *)Buffer;
      v9 = Buffer;
      v10 = 260;
      do
      {
        if ( v10 == -2147483386 )
          break;
        v11 = *(wchar_t *)((char *)v9 + v8);
        if ( !v11 )
          break;
        *v9++ = v11;
        --v10;
      }
      while ( v10 );
      v12 = v10 == 0;
      v13 = v9 - 1;
      if ( v10 )
        v13 = v9;
      *v13 = 0;
    }
    else
    {
      if ( !a5
        || (GetModuleFileNameW(0, Filename, 0x104u) & 0x80000000) != 0
        || wsplitpath_s_0(Filename, Drive, 3u, Dir, 0x100u, v22, 0x100u, Ext, 0x100u)
        || wmakepath_s_0(Buffer, 0x104u, Drive, Dir, ::Filename, L".dll") )
      {
        return;
      }
      v12 = GetFileAttributesW(Buffer) == -1;
    }
    if ( !v12 )
    {
      LibraryW = LoadLibraryW(Buffer);
      if ( LibraryW )
      {
        Attach(LibraryW);
        if ( gpSetPerformanceRegRoot )
          gpSetPerformanceRegRoot(a2);
        if ( gpfCodeMarker && gpfUnInitPerf )
        {
          if ( gpfInitPerf2 )
          {
            AddAtomW(lpString);
            gpfInitPerf2(a1, a2);
          }
          else if ( gpfInitPerf )
          {
            AddAtomW(lpString);
            gpfInitPerf(a1);
          }
        }
        v16 = 0;
        if ( GetPerformanceRegistryDwordValue(HKEY_LOCAL_MACHINE, a2, L"AutoStartupLoggingEndMarker", &v16) )
        {
          v15 = 0;
          v16 = 0;
        }
        else
        {
          v15 = v16;
        }
        if ( v15 )
          a4 = v15;
        if ( a4 )
          BeginCodeMarkerLogging(a4);
      }
    }
  }
}

```

## disassembly

```asm
0x14002524c  test    rdx, rdx
0x14002524f  jz      locret_1400254A8
0x140025255  mov     [rsp-8+arg_10], rbx
0x14002525a  push    rbp
0x14002525b  push    rsi
0x14002525c  push    rdi
0x14002525d  push    r14
0x14002525f  push    r15
0x140025261  lea     rbp, [rsp-990h]
0x140025269  sub     rsp, 0A90h
0x140025270  mov     rax, cs:__security_cookie
0x140025277  xor     rax, rsp
0x14002527a  mov     [rbp+9B0h+var_30], rax
0x140025281  xor     r15d, r15d
0x140025284  mov     edi, r9d
0x140025287  cmp     cs:?ghInstPerf@@3PEAUHINSTANCE__@@EA, r15; HINSTANCE__ * ghInstPerf
0x14002528e  mov     rsi, rdx
0x140025291  mov     r14d, ecx
0x140025294  jnz     loc_140025483
0x14002529a  mov     dl, r8b
0x14002529d  mov     rcx, rsi; unsigned __int16 *
0x1400252a0  call    FEnabledInRegistry
0x1400252a5  test    al, al
0x1400252a7  jz      short loc_1400252F8
0x1400252a9  mov     rdx, cs:off_14009D7C0; "Microsoft.Internal.Performance.CodeMark"...
0x1400252b0  lea     rax, [rsp+0AB0h+Buffer]
0x1400252b5  sub     rdx, rax
0x1400252b8  lea     rcx, [rsp+0AB0h+Buffer]
0x1400252bd  mov     ebx, 104h
0x1400252c2  lea     rax, [rbx+7FFFFEFAh]
0x1400252c9  test    rax, rax
0x1400252cc  jz      short loc_1400252E4
0x1400252ce  movzx   eax, word ptr [rdx+rcx]
0x1400252d2  test    ax, ax
0x1400252d5  jz      short loc_1400252E4
0x1400252d7  mov     [rcx], ax
0x1400252da  add     rcx, 2
0x1400252de  sub     rbx, 1
0x1400252e2  jnz     short loc_1400252C2
0x1400252e4  test    rbx, rbx
0x1400252e7  lea     rax, [rcx-2]
0x1400252eb  cmovnz  rax, rcx
0x1400252ef  mov     [rax], r15w
0x1400252f3  jmp     loc_1400253BA
0x1400252f8  cmp     [rbp+9B0h+arg_20], r15b
0x1400252ff  jz      loc_140025483
0x140025305  mov     ebx, 104h
0x14002530a  lea     rdx, [rbp+9B0h+Filename]; lpFilename
0x140025311  mov     r8d, ebx; nSize
0x140025314  xor     ecx, ecx; hModule
0x140025316  call    cs:__imp_GetModuleFileNameW
0x14002531c  test    eax, eax
0x14002531e  js      loc_140025483
0x140025324  lea     ecx, [rbx-4]
0x140025327  mov     r8d, 3; DriveCount
0x14002532d  mov     [rsp+0AB0h+ExtCount], rcx; ExtCount
0x140025332  lea     rax, [rbp+9B0h+var_430]
0x140025339  mov     [rsp+0AB0h+Ext], rax; Ext
0x14002533e  lea     r9, [rbp+9B0h+Dir]; Dir
0x140025345  mov     [rsp+0AB0h+FilenameCount], rcx; FilenameCount
0x14002534a  lea     rax, [rbp+9B0h+var_230]
0x140025351  mov     [rsp+0AB0h+var_A88], rax; Filename
0x140025356  lea     rdx, [rsp+0AB0h+Drive]; Drive
0x14002535b  mov     [rsp+0AB0h+DirCount], rcx; DirCount
0x140025360  lea     rcx, [rbp+9B0h+Filename]; FullPath
0x140025367  call    _wsplitpath_s_0
0x14002536c  test    eax, eax
0x14002536e  jnz     loc_140025483
0x140025374  lea     rax, aDll; ".dll"
0x14002537b  mov     edx, ebx; BufferCount
0x14002537d  mov     [rsp+0AB0h+var_A88], rax; Ext
0x140025382  lea     r9, [rbp+9B0h+Dir]; Dir
0x140025389  mov     rax, cs:Filename
0x140025390  lea     r8, [rsp+0AB0h+Drive]; Drive
0x140025395  lea     rcx, [rsp+0AB0h+Buffer]; Buffer
0x14002539a  mov     [rsp+0AB0h+DirCount], rax; Filename
0x14002539f  call    _wmakepath_s_0
0x1400253a4  test    eax, eax
0x1400253a6  jnz     loc_140025483
0x1400253ac  lea     rcx, [rsp+0AB0h+Buffer]; lpFileName
0x1400253b1  call    cs:__imp_GetFileAttributesW
0x1400253b7  cmp     eax, 0FFFFFFFFh
0x1400253ba  jz      loc_140025483
0x1400253c0  lea     rcx, [rsp+0AB0h+Buffer]; lpLibFileName
0x1400253c5  call    cs:__imp_LoadLibraryW
0x1400253cb  test    rax, rax
0x1400253ce  jz      loc_140025483
0x1400253d4  mov     rcx, rax; hModule
0x1400253d7  call    Attach
0x1400253dc  mov     rax, cs:?gpSetPerformanceRegRoot@@3P6AXPEBG@ZEA; void (*gpSetPerformanceRegRoot)(ushort const *)
0x1400253e3  test    rax, rax
0x1400253e6  jz      short loc_1400253ED
0x1400253e8  mov     rcx, rsi
0x1400253eb  call    rax ; void (*gpSetPerformanceRegRoot)(ushort const *)
0x1400253ed  cmp     cs:?gpfCodeMarker@@3P6AXHPEBXK@ZEA, r15; void (*gpfCodeMarker)(int,void const *,ulong)
0x1400253f4  jz      short loc_140025442
0x1400253f6  cmp     cs:?gpfUnInitPerf@@3P6AXH@ZEA, r15; void (*gpfUnInitPerf)(int)
0x1400253fd  jz      short loc_140025442
0x1400253ff  cmp     cs:?gpfInitPerf2@@3P6AXHPEBG@ZEA, r15; void (*gpfInitPerf2)(int,ushort const *)
0x140025406  jz      short loc_140025423
0x140025408  mov     rcx, cs:lpString; lpString
0x14002540f  call    cs:__imp_AddAtomW
0x140025415  mov     rdx, rsi
0x140025418  mov     ecx, r14d
0x14002541b  call    cs:?gpfInitPerf2@@3P6AXHPEBG@ZEA; void (*gpfInitPerf2)(int,ushort const *)
0x140025421  jmp     short loc_140025442
0x140025423  cmp     cs:?gpfInitPerf@@3P6AXH@ZEA, r15; void (*gpfInitPerf)(int)
0x14002542a  jz      short loc_140025442
0x14002542c  mov     rcx, cs:lpString; lpString
0x140025433  call    cs:__imp_AddAtomW
0x140025439  mov     ecx, r14d
0x14002543c  call    cs:?gpfInitPerf@@3P6AXH@ZEA; void (*gpfInitPerf)(int)
0x140025442  lea     r9, [rsp+0AB0h+var_A60]; unsigned int *
0x140025447  mov     [rsp+0AB0h+var_A60], r15d
0x14002544c  lea     r8, aAutostartuplog; "AutoStartupLoggingEndMarker"
0x140025453  mov     rdx, rsi; unsigned __int16 *
0x140025456  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x14002545d  call    ?GetPerformanceRegistryDwordValue@@YAJPEAUHKEY__@@PEBG1AEAK@Z; GetPerformanceRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong &)
0x140025462  test    eax, eax
0x140025464  jz      short loc_14002546F
0x140025466  mov     eax, r15d
0x140025469  mov     [rsp+0AB0h+var_A60], eax
0x14002546d  jmp     short loc_140025473
0x14002546f  mov     eax, [rsp+0AB0h+var_A60]
0x140025473  test    eax, eax
0x140025475  cmovnz  edi, eax
0x140025478  test    edi, edi
0x14002547a  jz      short loc_140025483
0x14002547c  mov     ecx, edi
0x14002547e  call    ?BeginCodeMarkerLogging@@YAJW4CodeMarkerEvent@Performance@Internal@Microsoft@@@Z; BeginCodeMarkerLogging(Microsoft::Internal::Performance::CodeMarkerEvent)
0x140025483  mov     rcx, [rbp+9B0h+var_30]
0x14002548a  xor     rcx, rsp; StackCookie
0x14002548d  call    __security_check_cookie
0x140025492  mov     rbx, [rsp+0AB0h+arg_10]
0x14002549a  add     rsp, 0A90h
0x1400254a1  pop     r15
0x1400254a3  pop     r14
0x1400254a5  pop     rdi
0x1400254a6  pop     rsi
0x1400254a7  pop     rbp
0x1400254a8  retn
```
