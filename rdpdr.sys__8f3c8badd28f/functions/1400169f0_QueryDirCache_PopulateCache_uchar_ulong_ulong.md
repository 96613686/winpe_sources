# QueryDirCache::PopulateCache(uchar *,ulong,ulong)

- ea: `0x1400169f0`
- end: `0x140016b14`
- name: `?PopulateCache@QueryDirCache@@QEAAHPEAEKK@Z`
- size: `292`
- prototype: `__int64 __fastcall(QueryDirCache *this, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140016b1c`

## callees

- `0x140003188`
- `0x14000324c`
- `0x14000327c`
- `0x1400032c0`
- `0x1400065c0`
- `0x1400167f4`
- `0x1400169f0`
- `0x140016ba8`

## pseudocode

```c
__int64 __fastcall QueryDirCache::PopulateCache(
        QueryDirCache *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned __int64 v5; // rbx
  QueryDirCache *v8; // rcx
  void *v9; // rax
  unsigned int *v10; // rax
  __int64 v11; // r9
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx

  v5 = a3;
  QueryDirCache::CleanupCache(this);
  v8 = (QueryDirCache *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids, (unsigned int)v5);
  if ( !(unsigned int)QueryDirCache::ValidateCacheBuffer(v8, a2, v5, a4) )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 0;
    v14 = 35;
    goto LABEL_16;
  }
  v9 = operator new(v5, 0x100u);
  *((_QWORD *)this + 1) = v9;
  if ( !v9 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 0;
    v14 = 34;
LABEL_16:
    WPP_SF_(v13->AttachedDevice, v14, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids);
    return 0;
  }
  memmove(v9, a2, v5);
  v10 = (unsigned int *)*((_QWORD *)this + 1);
  *((_DWORD *)this + 4) = v5;
  v11 = *v10;
  *((_QWORD *)this + 3) = v10 + 1;
  *((_QWORD *)this + 4) = (unsigned int)v11;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids, v11, v5);
  return 1;
}

```

## disassembly

```asm
0x1400169f0  push    rbx
0x1400169f2  push    rbp
0x1400169f3  push    rsi
0x1400169f4  push    rdi
0x1400169f5  push    r15
0x1400169f7  sub     rsp, 30h
0x1400169fb  mov     esi, r9d
0x1400169fe  mov     ebx, r8d
0x140016a01  mov     rbp, rdx
0x140016a04  mov     rdi, rcx
0x140016a07  call    ?CleanupCache@QueryDirCache@@QEAAXXZ; QueryDirCache::CleanupCache(void)
0x140016a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140016a13  lea     r15, WPP_GLOBAL_Control
0x140016a1a  cmp     rcx, r15
0x140016a1d  jz      short loc_140016A3D
0x140016a1f  cmp     byte ptr [rcx+29h], 5
0x140016a23  jb      short loc_140016A3D
0x140016a25  mov     rcx, [rcx+18h]
0x140016a29  lea     r8, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids
0x140016a30  mov     edx, 20h ; ' '
0x140016a35  mov     r9d, ebx
0x140016a38  call    WPP_SF_d
0x140016a3d  mov     r9d, esi; unsigned int
0x140016a40  mov     r8d, ebx; unsigned int
0x140016a43  mov     rdx, rbp; unsigned __int8 *
0x140016a46  call    ?ValidateCacheBuffer@QueryDirCache@@IEAAHPEAEKK@Z; QueryDirCache::ValidateCacheBuffer(uchar *,ulong,ulong)
0x140016a4b  test    eax, eax
0x140016a4d  jz      loc_140016ADF
0x140016a53  mov     edx, 100h; unsigned __int64
0x140016a58  mov     rcx, rbx; unsigned __int64
0x140016a5b  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x140016a60  mov     [rdi+8], rax
0x140016a64  test    rax, rax
0x140016a67  jz      short loc_140016AC6
0x140016a69  mov     r8, rbx; Size
0x140016a6c  mov     rdx, rbp; Src
0x140016a6f  mov     rcx, rax; void *
0x140016a72  call    memmove
0x140016a77  mov     rax, [rdi+8]
0x140016a7b  mov     [rdi+10h], ebx
0x140016a7e  mov     r9d, [rax]
0x140016a81  add     rax, 4
0x140016a85  mov     [rdi+18h], rax
0x140016a89  mov     [rdi+20h], r9d
0x140016a8d  mov     dword ptr [rdi+24h], 0
0x140016a94  mov     rcx, cs:WPP_GLOBAL_Control
0x140016a9b  cmp     rcx, r15
0x140016a9e  jz      short loc_140016ABF
0x140016aa0  cmp     byte ptr [rcx+29h], 5
0x140016aa4  jb      short loc_140016ABF
0x140016aa6  mov     rcx, [rcx+18h]
0x140016aaa  lea     r8, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids
0x140016ab1  mov     edx, 21h ; '!'
0x140016ab6  mov     [rsp+58h+var_38], ebx
0x140016aba  call    WPP_SF_dd
0x140016abf  mov     eax, 1
0x140016ac4  jmp     short loc_140016B08
0x140016ac6  mov     rcx, cs:WPP_GLOBAL_Control
0x140016acd  cmp     rcx, r15
0x140016ad0  jz      short loc_140016B06
0x140016ad2  cmp     byte ptr [rcx+29h], 2
0x140016ad6  jb      short loc_140016B06
0x140016ad8  mov     edx, 22h ; '"'
0x140016add  jmp     short loc_140016AF6
0x140016adf  mov     rcx, cs:WPP_GLOBAL_Control
0x140016ae6  cmp     rcx, r15
0x140016ae9  jz      short loc_140016B06
0x140016aeb  cmp     byte ptr [rcx+29h], 2
0x140016aef  jb      short loc_140016B06
0x140016af1  mov     edx, 23h ; '#'
0x140016af6  mov     rcx, [rcx+18h]
0x140016afa  lea     r8, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids
0x140016b01  call    WPP_SF_
0x140016b06  xor     eax, eax
0x140016b08  add     rsp, 30h
0x140016b0c  pop     r15
0x140016b0e  pop     rdi
0x140016b0f  pop     rsi
0x140016b10  pop     rbp
0x140016b11  pop     rbx
0x140016b12  retn
```
