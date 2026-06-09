# CScrub::_ScrubDirectoryFileEntry(_SCRUB_THREAD_CONTEXT *,void *,_FILE_ID_EXTD_DIR_INFORMATION const *,CFileName *,_SCRUB_DIRECTORY_ENTRY_FLAGS)

- ea: `0x180029210`
- end: `0x1800293cd`
- name: `?_ScrubDirectoryFileEntry@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXPEBU_FILE_ID_EXTD_DIR_INFORMATION@@PEAVCFileName@@W4_SCRUB_DIRECTORY_ENTRY_FLAGS@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(__int64, struct _SCRUB_THREAD_CONTEXT *, __int64, __int64, struct CFileName *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002892c`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x180023a44`
- `0x1800273d8`
- `0x180029210`
- `0x18002bb08`

## string_xrefs

- `0x180029247`: `CScrub::_ScrubDirectoryFileEntry`

## pseudocode

```c
__int64 __fastcall CScrub::_ScrubDirectoryFileEntry(
        __int64 a1,
        struct _SCRUB_THREAD_CONTEXT *a2,
        __int64 a3,
        __int64 a4,
        struct CFileName *a5)
{
  __int64 v9; // rdx
  unsigned int v10; // ebx
  USHORT v11; // dx
  USHORT Length; // cx
  USHORT v13; // ax
  int v14; // eax
  unsigned int v15; // esi
  struct _UNICODE_STRING v17; // [rsp+40h] [rbp-30h] BYREF
  USHORT v18; // [rsp+50h] [rbp-20h]
  USHORT v19; // [rsp+52h] [rbp-1Eh]
  int v20; // [rsp+54h] [rbp-1Ch]
  char *v21; // [rsp+58h] [rbp-18h]
  const char *v22; // [rsp+60h] [rbp-10h] BYREF
  int v23; // [rsp+68h] [rbp-8h]

  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v9 + 16) = "CScrub::_ScrubDirectoryFileEntry";
  v22 = "CScrub::_ScrubDirectoryFileEntry";
  v23 = 0;
  v10 = 1;
  v11 = ++*(_WORD *)(v9 + 8);
  Length = GlobalIndentString.Length;
  v13 = GlobalIndentString.Length;
  if ( v11 < GlobalIndentString.Length )
    v13 = v11;
  v18 = v13;
  if ( v11 < GlobalIndentString.Length )
    Length = v11;
  v19 = Length;
  v20 = 0;
  v21 = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrub::_ScrubDirectoryFileEntry");
  }
  *(_QWORD *)&v17.Length = 0;
  v17.Buffer = (PWSTR)(a4 + 88);
  v17.MaximumLength = *(_WORD *)(a4 + 60);
  v17.Length = v17.MaximumLength;
  CScrub::_Checkpoint((RTL_SRWLOCK *)a1, a2, a5, &v17, *(_BYTE *)(a1 + 1496));
  *(_BYTE *)(a1 + 1496) = 0;
  v14 = *(_DWORD *)(a4 + 56);
  if ( (v14 & 0x20000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZZZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)a1 + 36LL),
        *(_QWORD *)(*(_QWORD *)a1 + 64LL),
        (__int64)a2 + 88,
        (__int64)&v17);
    }
    v23 = 1;
  }
  else
  {
    v15 = CScrub::ScrubFile(a1, a2, a3, &v17, v14);
    v23 = v15;
    if ( v15 == -805306102 )
      CScrub::_Checkpoint((RTL_SRWLOCK *)a1, a2, a5, &v17, 1u);
    v10 = v15;
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v22);
  return v10;
}

```

## disassembly

```asm
0x180029210  push    rbp
0x180029212  push    rbx
0x180029213  push    rsi
0x180029214  push    rdi
0x180029215  push    r13
0x180029217  push    r14
0x180029219  push    r15
0x18002921b  mov     rbp, rsp
0x18002921e  sub     rsp, 70h
0x180029222  mov     rsi, r9
0x180029225  mov     r15, r8
0x180029228  mov     r14, rdx
0x18002922b  mov     rdi, rcx
0x18002922e  mov     r10d, cs:_tls_index
0x180029235  mov     rax, gs:58h
0x18002923e  mov     rdx, [rax+r10*8]
0x180029242  mov     eax, 10h
0x180029247  lea     r8, aCscrubScrubdir_1; "CScrub::_ScrubDirectoryFileEntry"
0x18002924e  mov     [rax+rdx], r8
0x180029252  mov     [rbp+var_10], r8
0x180029256  mov     [rbp+var_8], 0
0x18002925d  mov     eax, 8
0x180029262  mov     ebx, 1
0x180029267  add     [rax+rdx], bx
0x18002926b  movzx   edx, word ptr [rax+rdx]
0x18002926f  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180029276  movzx   eax, cx
0x180029279  cmp     dx, cx
0x18002927c  cmovb   ax, dx
0x180029280  mov     [rbp+var_20], ax
0x180029284  cmovb   cx, dx
0x180029288  mov     [rbp+var_1E], cx
0x18002928c  xor     eax, eax
0x18002928e  mov     [rbp+var_1C], eax
0x180029291  mov     rax, cs:off_180047060; "                                       "...
0x180029298  mov     [rbp+var_18], rax
0x18002929c  lea     r13, WPP_GLOBAL_Control
0x1800292a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800292aa  cmp     rcx, r13
0x1800292ad  jz      short loc_1800292D0
0x1800292af  test    [rcx+1Ch], bl
0x1800292b2  jz      short loc_1800292D0
0x1800292b4  cmp     byte ptr [rcx+19h], 5
0x1800292b8  jb      short loc_1800292D0
0x1800292ba  lea     edx, [rbx+0Ch]
0x1800292bd  mov     qword ptr [rsp+70h+var_50], r8; __int64
0x1800292c2  lea     r9, [rbp+var_20]
0x1800292c6  mov     rcx, [rcx+10h]; LoggerHandle
0x1800292ca  call    WPP_SF_aZs
0x1800292cf  nop
0x1800292d0  xorps   xmm0, xmm0
0x1800292d3  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x1800292d7  lea     rax, [rsi+58h]
0x1800292db  mov     [rbp+var_30.Buffer], rax
0x1800292df  movzx   eax, word ptr [rsi+3Ch]
0x1800292e3  mov     [rbp+var_30.MaximumLength], ax
0x1800292e7  mov     [rbp+var_30.Length], ax
0x1800292eb  mov     al, [rdi+5D8h]
0x1800292f1  mov     [rsp+70h+var_50], al; unsigned __int8
0x1800292f5  lea     r9, [rbp+var_30]; struct _UNICODE_STRING *
0x1800292f9  mov     r8, [rbp+arg_20]; struct CFileName *
0x1800292fd  mov     rdx, r14; struct _SCRUB_THREAD_CONTEXT *
0x180029300  mov     rcx, rdi; this
0x180029303  call    ?_Checkpoint@CScrub@@AEAAXPEAU_SCRUB_THREAD_CONTEXT@@PEAVCFileName@@PEBU_UNICODE_STRING@@E@Z; CScrub::_Checkpoint(_SCRUB_THREAD_CONTEXT *,CFileName *,_UNICODE_STRING const *,uchar)
0x180029308  mov     byte ptr [rdi+5D8h], 0
0x18002930f  mov     eax, [rsi+38h]
0x180029312  bt      eax, 11h
0x180029316  jnb     short loc_18002936F
0x180029318  mov     rcx, cs:WPP_GLOBAL_Control
0x18002931f  cmp     rcx, r13
0x180029322  jz      short loc_18002936A
0x180029324  test    [rcx+1Ch], bl
0x180029327  jz      short loc_18002936A
0x180029329  cmp     byte ptr [rcx+19h], 4
0x18002932d  jb      short loc_18002936A
0x18002932f  mov     r8, [rdi]
0x180029332  mov     r9, [r8]
0x180029335  lea     rax, [r14+58h]
0x180029339  mov     edx, 0AAh
0x18002933e  lea     r10, [rbp+var_30]
0x180029342  mov     [rsp+70h+var_38], r10; __int64
0x180029347  mov     [rsp+70h+var_40], rax; __int64
0x18002934c  mov     rax, [r8+40h]
0x180029350  mov     [rsp+70h+var_48], rax; __int64
0x180029355  mov     eax, [r9+24h]
0x180029359  mov     dword ptr [rsp+70h+var_50], eax; char
0x18002935d  mov     r9d, [r9+10h]
0x180029361  mov     rcx, [rcx+10h]; LoggerHandle
0x180029365  call    WPP_SF_DDZZZ
0x18002936a  mov     [rbp+var_8], ebx
0x18002936d  jmp     short loc_1800293B3
0x18002936f  mov     [rsp+70h+var_40], 0
0x180029378  mov     dword ptr [rsp+70h+var_50], eax
0x18002937c  lea     r9, [rbp+var_30]
0x180029380  mov     r8, r15
0x180029383  mov     rdx, r14
0x180029386  mov     rcx, rdi
0x180029389  call    ?ScrubFile@CScrub@@QEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXPEBU_UNICODE_STRING@@KW4_SCRUB_DIRECTORY_ENTRY_FLAGS@@PEAU_SCRUB_FILE_ENTRY@@@Z; CScrub::ScrubFile(_SCRUB_THREAD_CONTEXT *,void *,_UNICODE_STRING const *,ulong,_SCRUB_DIRECTORY_ENTRY_FLAGS,_SCRUB_FILE_ENTRY *)
0x18002938e  mov     esi, eax
0x180029390  mov     [rbp+var_8], eax
0x180029393  cmp     eax, 0D000010Ah
0x180029398  jnz     short loc_1800293B1
0x18002939a  mov     [rsp+70h+var_50], bl; unsigned __int8
0x18002939e  lea     r9, [rbp+var_30]; struct _UNICODE_STRING *
0x1800293a2  mov     r8, [rbp+arg_20]; struct CFileName *
0x1800293a6  mov     rdx, r14; struct _SCRUB_THREAD_CONTEXT *
0x1800293a9  mov     rcx, rdi; this
0x1800293ac  call    ?_Checkpoint@CScrub@@AEAAXPEAU_SCRUB_THREAD_CONTEXT@@PEAVCFileName@@PEBU_UNICODE_STRING@@E@Z; CScrub::_Checkpoint(_SCRUB_THREAD_CONTEXT *,CFileName *,_UNICODE_STRING const *,uchar)
0x1800293b1  mov     ebx, esi
0x1800293b3  lea     rcx, [rbp+var_10]; this
0x1800293b7  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1800293bc  mov     eax, ebx
0x1800293be  add     rsp, 70h
0x1800293c2  pop     r15
0x1800293c4  pop     r14
0x1800293c6  pop     r13
0x1800293c8  pop     rdi
0x1800293c9  pop     rsi
0x1800293ca  pop     rbx
0x1800293cb  pop     rbp
0x1800293cc  retn
```
