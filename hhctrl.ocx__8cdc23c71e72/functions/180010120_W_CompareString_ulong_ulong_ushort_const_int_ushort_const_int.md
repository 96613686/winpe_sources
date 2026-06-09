# W_CompareString(ulong,ulong,ushort const *,int,ushort const *,int)

- ea: `0x180010120`
- end: `0x1800102ce`
- name: `?W_CompareString@@YAHKKPEBGH0H@Z`
- size: `430`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, int@<r9d>, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003dad0`
- `0x1800432b0`

## callees

- `0x18000c02c`
- `0x180010120`
- `0x180011424`
- `0x180064990`
- `0x180075c36`

## import_xrefs

- `msvcrt!malloc` at `0x1800101ba`
- `msvcrt!malloc` at `0x1800101d3`
- `msvcrt!malloc` at `0x1800101ba`
- `msvcrt!malloc` at `0x1800101d3`
- `msvcrt!free` at `0x1800102a5`
- `msvcrt!free` at `0x1800102ae`
- `msvcrt!free` at `0x1800102a5`
- `msvcrt!free` at `0x1800102ae`
- `KERNEL32!CompareStringW` at `0x180010164`
- `KERNEL32!CompareStringW` at `0x180010164`
- `KERNEL32!CompareStringA` at `0x180010273`
- `KERNEL32!CompareStringA` at `0x180010273`
- `KERNEL32!lstrlenW` at `0x180010190`
- `KERNEL32!lstrlenW` at `0x18001019b`
- `KERNEL32!lstrlenW` at `0x180010190`
- `KERNEL32!lstrlenW` at `0x18001019b`
- `KERNEL32!GetLastError` at `0x180010174`
- `KERNEL32!GetLastError` at `0x180010174`

## pseudocode

```c
__int64 __fastcall W_CompareString(
        LCID a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 a4,
        const unsigned __int16 *lpString)
{
  unsigned int v7; // ebx
  int v8; // esi
  int v9; // ebp
  int v10; // ebx
  CHAR *v11; // r13
  CHAR *v12; // rax
  CHAR *lpString2; // r12
  unsigned int v14; // edi
  int v15; // ebx
  int cchCount2; // eax
  int v17; // eax
  int v18; // ebx
  int v21; // [rsp+88h] [rbp+10h]
  int v22; // [rsp+98h] [rbp+20h]

  if ( !g_fAnsiAPIs )
  {
    v7 = CompareStringW(a1, 0, a3, -1, lpString, -1);
    if ( v7 || GetLastError() != 120 )
      return v7;
    g_fAnsiAPIs = 1;
  }
  v8 = lstrlenW(a3);
  v9 = lstrlenW(lpString);
  v10 = W_cbchMaxAcp();
  v22 = v10 * (v8 + 1);
  v11 = (CHAR *)malloc(v22);
  v21 = v10 * (v9 + 1);
  v12 = (CHAR *)malloc(v21);
  lpString2 = v12;
  if ( v11 && v12 )
  {
    v14 = CodePageFromLCID(a1);
    v15 = HHWideCharToMultiByte(v14, 0, a3, v8, v11, v22, 0, 0);
    cchCount2 = HHWideCharToMultiByte(v14, 0, lpString, v9, lpString2, v21, 0, 0);
    v7 = CompareStringA(a1, 0, v11, v15, lpString2, cchCount2);
  }
  else
  {
    v17 = v8;
    if ( v8 >= v9 )
      v17 = v9;
    v18 = memcmp_0(a3, lpString, 2LL * v17);
    if ( !v18 )
      v18 = v8 - v9;
    v7 = v18 + 2;
  }
  free(v11);
  free(lpString2);
  return v7;
}

```

## disassembly

```asm
0x180010120  mov     rax, rsp
0x180010123  mov     [rax+18h], rbx
0x180010127  mov     [rax+20h], r9d
0x18001012b  mov     [rax+10h], edx
0x18001012e  mov     [rax+8], ecx
0x180010131  push    rbp
0x180010132  push    rsi
0x180010133  push    rdi
0x180010134  push    r12
0x180010136  push    r13
0x180010138  push    r14
0x18001013a  push    r15
0x18001013c  sub     rsp, 40h
0x180010140  cmp     cs:?g_fAnsiAPIs@@3HA, 0; int g_fAnsiAPIs
0x180010147  mov     r14, r8
0x18001014a  mov     r15, [rsp+78h+lpString]
0x180010152  mov     edi, ecx
0x180010154  jnz     short loc_18001018D
0x180010156  or      r9d, 0FFFFFFFFh; cchCount1
0x18001015a  xor     edx, edx; dwCmpFlags
0x18001015c  mov     [rax-50h], r9d
0x180010160  mov     [rax-58h], r15
0x180010164  call    cs:__imp_CompareStringW
0x18001016a  mov     ebx, eax
0x18001016c  test    eax, eax
0x18001016e  jnz     loc_1800102B4
0x180010174  call    cs:__imp_GetLastError
0x18001017a  cmp     eax, 78h ; 'x'
0x18001017d  jnz     loc_1800102B4
0x180010183  mov     cs:?g_fAnsiAPIs@@3HA, 1; int g_fAnsiAPIs
0x18001018d  mov     rcx, r14; lpString
0x180010190  call    cs:__imp_lstrlenW
0x180010196  mov     rcx, r15; lpString
0x180010199  mov     esi, eax
0x18001019b  call    cs:__imp_lstrlenW
0x1800101a1  mov     ebp, eax
0x1800101a3  call    ?W_cbchMaxAcp@@YAHXZ; W_cbchMaxAcp(void)
0x1800101a8  mov     ebx, eax
0x1800101aa  lea     eax, [rsi+1]
0x1800101ad  imul    eax, ebx
0x1800101b0  movsxd  rcx, eax; Size
0x1800101b3  mov     [rsp+78h+arg_18], eax
0x1800101ba  call    cs:__imp_malloc
0x1800101c0  mov     r13, rax
0x1800101c3  lea     eax, [rbp+1]
0x1800101c6  imul    eax, ebx
0x1800101c9  movsxd  rcx, eax; Size
0x1800101cc  mov     [rsp+78h+arg_8], eax
0x1800101d3  call    cs:__imp_malloc
0x1800101d9  mov     r12, rax
0x1800101dc  test    r13, r13
0x1800101df  jz      loc_18001027D
0x1800101e5  test    rax, rax
0x1800101e8  jz      loc_18001027D
0x1800101ee  mov     ecx, edi; unsigned int
0x1800101f0  call    ?CodePageFromLCID@@YAIK@Z; CodePageFromLCID(ulong)
0x1800101f5  mov     edi, eax
0x1800101f7  mov     [rsp+78h+var_40], 0; LPBOOL
0x180010200  mov     eax, [rsp+78h+arg_18]
0x180010207  mov     ecx, edi; unsigned int
0x180010209  mov     [rsp+78h+var_48], 0; LPCCH
0x180010212  mov     r9d, esi; int
0x180010215  mov     [rsp+78h+cchCount2], eax; int
0x180010219  mov     r8, r14; unsigned __int16 *
0x18001021c  xor     edx, edx; unsigned int
0x18001021e  mov     [rsp+78h+lpString2], r13; LPSTR
0x180010223  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x180010228  mov     [rsp+78h+var_40], 0; LPBOOL
0x180010231  mov     ebx, eax
0x180010233  mov     eax, [rsp+78h+arg_8]
0x18001023a  mov     r9d, ebp; int
0x18001023d  mov     [rsp+78h+var_48], 0; LPCCH
0x180010246  mov     r8, r15; unsigned __int16 *
0x180010249  mov     [rsp+78h+cchCount2], eax; int
0x18001024d  xor     edx, edx; unsigned int
0x18001024f  mov     ecx, edi; unsigned int
0x180010251  mov     [rsp+78h+lpString2], r12; LPSTR
0x180010256  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x18001025b  mov     ecx, [rsp+78h+Locale]; Locale
0x180010262  mov     r9d, ebx; cchCount1
0x180010265  mov     [rsp+78h+cchCount2], eax; cchCount2
0x180010269  mov     r8, r13; lpString1
0x18001026c  xor     edx, edx; dwCmpFlags
0x18001026e  mov     [rsp+78h+lpString2], r12; lpString2
0x180010273  call    cs:__imp_CompareStringA
0x180010279  mov     ebx, eax
0x18001027b  jmp     short loc_1800102A2
0x18001027d  mov     eax, esi
0x18001027f  cmp     esi, ebp
0x180010281  mov     rdx, r15; Buf2
0x180010284  mov     rcx, r14; Buf1
0x180010287  cmovge  eax, ebp
0x18001028a  movsxd  r8, eax
0x18001028d  add     r8, r8; Size
0x180010290  call    memcmp_0
0x180010295  mov     ebx, eax
0x180010297  test    eax, eax
0x180010299  jnz     short loc_18001029F
0x18001029b  mov     ebx, esi
0x18001029d  sub     ebx, ebp
0x18001029f  add     ebx, 2
0x1800102a2  mov     rcx, r13; Block
0x1800102a5  call    cs:__imp_free
0x1800102ab  mov     rcx, r12; Block
0x1800102ae  call    cs:__imp_free
0x1800102b4  mov     eax, ebx
0x1800102b6  mov     rbx, [rsp+78h+arg_10]
0x1800102be  add     rsp, 40h
0x1800102c2  pop     r15
0x1800102c4  pop     r14
0x1800102c6  pop     r13
0x1800102c8  pop     r12
0x1800102ca  pop     rdi
0x1800102cb  pop     rsi
0x1800102cc  pop     rbp
0x1800102cd  retn
```
