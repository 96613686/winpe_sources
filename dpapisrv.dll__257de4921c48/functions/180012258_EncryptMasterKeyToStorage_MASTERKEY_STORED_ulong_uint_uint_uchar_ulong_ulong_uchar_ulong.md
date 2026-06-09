# EncryptMasterKeyToStorage(MASTERKEY_STORED *,ulong,uint,uint,uchar *,ulong,ulong,uchar *,ulong)

- ea: `0x180012258`
- end: `0x1800123e2`
- name: `?EncryptMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KIIPEAEKK1K@Z`
- size: `394`
- prototype: `__int64 __fastcall(struct MASTERKEY_STORED *, unsigned int, int, unsigned int, unsigned __int8 *, ULONG, char, unsigned __int8 *, size_t)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000e9c0`
- `0x1800180cc`
- `0x18002ac04`
- `0x18002d8f0`
- `0x18002ea4c`

## callees

- `0x180007f10`
- `0x18000b638`
- `0x18001199c`
- `0x180012258`
- `0x180012da4`
- `0x18001eb8c`
- `0x18002f510`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800123c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800123c6`

## string_xrefs

- `0x180012340`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18001238d`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall EncryptMasterKeyToStorage(
        struct MASTERKEY_STORED *a1,
        unsigned int a2,
        int a3,
        unsigned int a4,
        unsigned __int8 *a5,
        ULONG a6,
        char a7,
        unsigned __int8 *a8,
        size_t a9)
{
  unsigned int IterationCount; // ebx
  ULONG v14; // eax
  int v15; // edx
  ULONG v16; // ebx
  ULONG v17; // eax
  _BYTE *v18; // rcx
  __int64 v19; // rax
  size_t Size; // [rsp+30h] [rbp-68h]
  unsigned int v22; // [rsp+50h] [rbp-48h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-40h] BYREF

  IterationCount = 1;
  hMem = 0;
  v22 = 0;
  if ( (a7 & 1) == 0 && a2 <= 1 )
    IterationCount = GetIterationCount(a4);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_SSd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), a2, a3, (_DWORD)a1 + 16, *((_QWORD *)a1 + 1), IterationCount);
  LODWORD(Size) = a9;
  v14 = EncryptMasterKeyToMemory(a3, a4, a5, a6, IterationCount, a8, Size, (unsigned __int8 **)&hMem, &v22);
  v16 = v14;
  if ( v14 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v15,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwLastError",
        v14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        175);
  }
  else
  {
    v17 = PersistMasterKeyToStorage(a1, a2, (unsigned __int8 *)hMem, v22);
    v16 = v17;
    if ( v17 )
      DebugTraceError(v17, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 4796);
    v18 = hMem;
    if ( hMem )
    {
      v19 = v22;
      if ( v22 )
      {
        do
        {
          *v18++ = 0;
          --v19;
        }
        while ( v19 );
        v18 = hMem;
      }
      LocalFree(v18);
    }
  }
  return v16;
}

```

## disassembly

```asm
0x180012258  push    rbx
0x18001225a  push    rbp
0x18001225b  push    rsi
0x18001225c  push    rdi
0x18001225d  push    r12
0x18001225f  push    r14
0x180012261  sub     rsp, 68h
0x180012265  mov     eax, dword ptr [rsp+98h+arg_30]
0x18001226c  mov     ebx, 1
0x180012271  mov     [rsp+98h+hMem], 0
0x18001227a  mov     ebp, r9d
0x18001227d  mov     [rsp+98h+var_48], 0
0x180012285  mov     r14d, r8d
0x180012288  mov     esi, edx
0x18001228a  mov     rdi, rcx
0x18001228d  test    bl, al
0x18001228f  jnz     short loc_18001229F
0x180012291  cmp     edx, ebx
0x180012293  ja      short loc_18001229F
0x180012295  mov     ecx, r9d; unsigned int
0x180012298  call    ?GetIterationCount@@YAKI@Z; GetIterationCount(uint)
0x18001229d  mov     ebx, eax
0x18001229f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122a6  lea     r12, WPP_GLOBAL_Control
0x1800122ad  cmp     rcx, r12
0x1800122b0  jz      short loc_1800122D2
0x1800122b2  test    byte ptr [rcx+1Ch], 4
0x1800122b6  jz      short loc_1800122D2
0x1800122b8  mov     rax, [rdi+8]
0x1800122bc  lea     r9, [rdi+10h]
0x1800122c0  mov     rcx, [rcx+10h]
0x1800122c4  mov     dword ptr [rsp+98h+var_70], ebx
0x1800122c8  mov     qword ptr [rsp+98h+var_78], rax
0x1800122cd  call    WPP_SF_SSd
0x1800122d2  mov     r9d, [rsp+98h+arg_28]; unsigned int
0x1800122da  lea     rax, [rsp+98h+var_48]
0x1800122df  mov     r8, [rsp+98h+arg_20]; unsigned __int8 *
0x1800122e7  mov     edx, ebp; unsigned int
0x1800122e9  mov     [rsp+98h+var_58], rax; unsigned int *
0x1800122ee  mov     ecx, r14d; unsigned int
0x1800122f1  lea     rax, [rsp+98h+hMem]
0x1800122f6  mov     [rsp+98h+var_60], rax; unsigned __int8 **
0x1800122fb  mov     eax, dword ptr [rsp+98h+arg_40]
0x180012302  mov     dword ptr [rsp+98h+Size], eax; Size
0x180012306  mov     rax, [rsp+98h+arg_38]
0x18001230e  mov     [rsp+98h+var_70], rax; unsigned __int8 *
0x180012313  mov     [rsp+98h+var_78], ebx; unsigned int
0x180012317  call    ?EncryptMasterKeyToMemory@@YAKIIPEAEKK0KPEAPEAEPEAK@Z; EncryptMasterKeyToMemory(uint,uint,uchar *,ulong,ulong,uchar *,ulong,uchar * *,ulong *)
0x18001231c  mov     ebx, eax
0x18001231e  test    eax, eax
0x180012320  jz      short loc_18001236D
0x180012322  mov     rcx, cs:WPP_GLOBAL_Control
0x180012329  cmp     rcx, r12
0x18001232c  jz      loc_1800123D2
0x180012332  test    byte ptr [rcx+1Ch], 1
0x180012336  jz      loc_1800123D2
0x18001233c  mov     rcx, [rcx+10h]
0x180012340  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180012347  mov     dword ptr [rsp+98h+Size], 12AFh
0x18001234f  lea     r9, aDwlasterror; "dwLastError"
0x180012356  mov     [rsp+98h+var_70], r8
0x18001235b  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180012362  mov     [rsp+98h+var_78], eax
0x180012366  call    WPP_SF_sDsd
0x18001236b  jmp     short loc_1800123D2
0x18001236d  mov     r9d, [rsp+98h+var_48]; unsigned int
0x180012372  mov     edx, esi; unsigned int
0x180012374  mov     r8, [rsp+98h+hMem]; unsigned __int8 *
0x180012379  mov     rcx, rdi; struct MASTERKEY_STORED *
0x18001237c  call    ?PersistMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KPEAEK@Z; PersistMasterKeyToStorage(MASTERKEY_STORED *,ulong,uchar *,ulong)
0x180012381  mov     ebx, eax
0x180012383  test    eax, eax
0x180012385  jz      short loc_1800123A2
0x180012387  mov     r9d, 12BCh
0x18001238d  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180012394  lea     rdx, aDwlasterror; "dwLastError"
0x18001239b  mov     ecx, eax
0x18001239d  call    DebugTraceError
0x1800123a2  mov     rcx, [rsp+98h+hMem]
0x1800123a7  test    rcx, rcx
0x1800123aa  jz      short loc_1800123D2
0x1800123ac  mov     eax, [rsp+98h+var_48]
0x1800123b0  test    rax, rax
0x1800123b3  jz      short loc_1800123C6
0x1800123b5  mov     byte ptr [rcx], 0
0x1800123b8  inc     rcx
0x1800123bb  sub     rax, 1
0x1800123bf  jnz     short loc_1800123B5
0x1800123c1  mov     rcx, [rsp+98h+hMem]; hMem
0x1800123c6  call    cs:__imp_LocalFree
0x1800123cd  nop     dword ptr [rax+rax+00h]
0x1800123d2  mov     eax, ebx
0x1800123d4  add     rsp, 68h
0x1800123d8  pop     r14
0x1800123da  pop     r12
0x1800123dc  pop     rdi
0x1800123dd  pop     rsi
0x1800123de  pop     rbp
0x1800123df  pop     rbx
0x1800123e0  retn
```
