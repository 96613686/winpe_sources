# PAL_System_Win32_GetModuleSpecificClassName(ushort const *,ushort *,ulong)

- ea: `0x18002b4b8`
- end: `0x18002b55e`
- name: `?PAL_System_Win32_GetModuleSpecificClassName@@YAJPEBGPEAGK@Z`
- size: `166`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002a33c`
- `0x18002a608`
- `0x18002a888`
- `0x18002ab18`

## callees

- `0x180006098`
- `0x18001d114`
- `0x18001ef44`
- `0x18002b4b8`

## string_xrefs

- `0x18002b4dd`: `PAL_SYS_WIN32_THREAD_WNDCLASS`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_GetModuleSpecificClassName(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  int v2; // ebx
  int CurrentThreadActivityIdPrefix; // eax

  if ( a2 )
  {
    *a2 = 0;
    v2 = StringCchPrintfW(a2, 0x104u, L"%p-%s", &g_TsSystemPalDllModule, L"PAL_SYS_WIN32_THREAD_WNDCLASS");
    if ( v2 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_9e2d2381f4b936a6413120d345f767e7_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"Failed StringCchPrintf",
        v2);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002b4b8  push    rbx
0x18002b4ba  sub     rsp, 30h
0x18002b4be  mov     r10, rdx
0x18002b4c1  test    rdx, rdx
0x18002b4c4  jz      loc_18002B551
0x18002b4ca  xor     eax, eax
0x18002b4cc  lea     r9, ?g_TsSystemPalDllModule@@3HA; int g_TsSystemPalDllModule
0x18002b4d3  mov     [rdx], ax
0x18002b4d6  lea     r8, aPS; "%p-%s"
0x18002b4dd  lea     rax, aPalSysWin32Thr; "PAL_SYS_WIN32_THREAD_WNDCLASS"
0x18002b4e4  mov     edx, 104h; unsigned __int64
0x18002b4e9  mov     rcx, r10; unsigned __int16 *
0x18002b4ec  mov     [rsp+38h+var_18], rax
0x18002b4f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002b4f6  mov     ebx, eax
0x18002b4f8  test    eax, eax
0x18002b4fa  jns     short loc_18002B556
0x18002b4fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b503  lea     rax, WPP_GLOBAL_Control
0x18002b50a  cmp     rcx, rax
0x18002b50d  jz      short loc_18002B556
0x18002b50f  test    byte ptr [rcx+1Ch], 8
0x18002b513  jz      short loc_18002B556
0x18002b515  cmp     byte ptr [rcx+19h], 2
0x18002b519  jb      short loc_18002B556
0x18002b51b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002b520  lea     rcx, aFailedStringcc; "Failed StringCchPrintf"
0x18002b527  mov     [rsp+38h+var_10], ebx
0x18002b52b  mov     [rsp+38h+var_18], rcx
0x18002b530  lea     r8, WPP_9e2d2381f4b936a6413120d345f767e7_Traceguids
0x18002b537  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b53e  mov     edx, 0Ch
0x18002b543  mov     r9d, eax
0x18002b546  mov     rcx, [rcx+10h]
0x18002b54a  call    WPP_SF_DsD
0x18002b54f  jmp     short loc_18002B556
0x18002b551  mov     ebx, 80070057h
0x18002b556  mov     eax, ebx
0x18002b558  add     rsp, 30h
0x18002b55c  pop     rbx
0x18002b55d  retn
```
