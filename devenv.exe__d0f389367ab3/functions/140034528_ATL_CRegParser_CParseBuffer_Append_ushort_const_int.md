# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x140034528`
- end: `0x14003465c`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `308`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14003465c`

## callees

- `0x140001040`
- `0x140002140`
- `0x140033ab0`
- `0x140034528`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14003464b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14003464b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1400345d6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14003463f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1400345d6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14003463f`
- `ole32!CoTaskMemRealloc` at `0x140034595`
- `ole32!CoTaskMemRealloc` at `0x140034595`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v4; // rbp
  int v6; // ecx
  int v7; // eax
  unsigned __int64 v8; // rdx
  LPVOID v9; // rax
  int v10; // ecx
  int v11; // eax
  size_t v12; // rsi
  void *v13; // rcx
  unsigned __int64 v14; // rdi

  v4 = a3;
  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 <= *(_DWORD *)this || v6 <= a3 )
    return 0;
  v7 = *((_DWORD *)this + 1);
  if ( v6 >= v7 )
  {
    do
    {
      if ( v7 > 0x3FFFFFFF )
        return 0;
      v7 *= 2;
      *((_DWORD *)this + 1) = v7;
    }
    while ( v6 >= v7 );
    v8 = 2LL * (unsigned int)v7;
    if ( v8 > 0xFFFFFFFF )
      return 0;
    v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
    if ( !v9 )
      return 0;
    *((_QWORD *)this + 1) = v9;
  }
  if ( *(int *)this < 0 )
    return 0;
  v10 = *((_DWORD *)this + 1);
  if ( *(_DWORD *)this >= v10 )
    return 0;
  v11 = v10 - *(_DWORD *)this;
  if ( v11 > v10 )
    return 0;
  v12 = 2LL * v11;
  v13 = (void *)(*((_QWORD *)this + 1) + 2LL * *(int *)this);
  v14 = 2 * v4;
  if ( 2 * v4 )
  {
    if ( !v13 )
      goto LABEL_14;
    if ( !a2 || v12 < v14 )
    {
      memset_0(v13, 0, v12);
      if ( a2 )
      {
        if ( v12 >= v14 )
          goto LABEL_25;
        *_errno() = 34;
LABEL_24:
        _invalid_parameter_noinfo();
LABEL_25:
        ATL::AtlThrowImpl(-2147024809);
      }
LABEL_14:
      *_errno() = 22;
      goto LABEL_24;
    }
    memcpy_0(v13, a2, 2 * v4);
  }
  *(_DWORD *)this += v4;
  *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
  return 1;
}

```

## disassembly

```asm
0x140034528  mov     [rsp+arg_0], rbx
0x14003452d  mov     [rsp+arg_8], rbp
0x140034532  mov     [rsp+arg_10], rsi
0x140034537  push    rdi
0x140034538  push    r14
0x14003453a  push    r15
0x14003453c  sub     rsp, 20h
0x140034540  mov     rbx, rcx
0x140034543  movsxd  rbp, r8d
0x140034546  mov     r14, rdx
0x140034549  lea     ecx, [rbp+1]
0x14003454c  add     ecx, [rbx]
0x14003454e  cmp     ecx, [rbx]
0x140034550  jle     loc_14003461F
0x140034556  cmp     ecx, ebp
0x140034558  jle     loc_14003461F
0x14003455e  mov     eax, [rbx+4]
0x140034561  xor     r15d, r15d
0x140034564  cmp     ecx, eax
0x140034566  jl      short loc_1400345A4
0x140034568  cmp     eax, 3FFFFFFFh
0x14003456d  jg      loc_14003461F
0x140034573  add     eax, eax
0x140034575  mov     [rbx+4], eax
0x140034578  cmp     ecx, eax
0x14003457a  jge     short loc_140034568
0x14003457c  mov     edx, eax
0x14003457e  mov     eax, 0FFFFFFFFh
0x140034583  add     rdx, rdx
0x140034586  cmp     rdx, rax
0x140034589  ja      loc_14003461F
0x14003458f  mov     rcx, [rbx+8]; pv
0x140034593  mov     edx, edx; cb
0x140034595  call    cs:__imp_CoTaskMemRealloc
0x14003459b  test    rax, rax
0x14003459e  jz      short loc_14003461F
0x1400345a0  mov     [rbx+8], rax
0x1400345a4  cmp     [rbx], r15d
0x1400345a7  jl      short loc_14003461F
0x1400345a9  mov     ecx, [rbx+4]
0x1400345ac  cmp     [rbx], ecx
0x1400345ae  jge     short loc_14003461F
0x1400345b0  mov     eax, ecx
0x1400345b2  sub     eax, [rbx]
0x1400345b4  cmp     eax, ecx
0x1400345b6  jg      short loc_14003461F
0x1400345b8  movsxd  rcx, dword ptr [rbx]
0x1400345bb  mov     rdi, rbp
0x1400345be  movsxd  rsi, eax
0x1400345c1  mov     rax, [rbx+8]
0x1400345c5  add     rsi, rsi
0x1400345c8  lea     rcx, [rax+rcx*2]; void *
0x1400345cc  add     rdi, rdi
0x1400345cf  jz      short loc_1400345F9
0x1400345d1  test    rcx, rcx
0x1400345d4  jnz     short loc_1400345E4
0x1400345d6  call    cs:__imp__errno
0x1400345dc  mov     dword ptr [rax], 16h
0x1400345e2  jmp     short loc_14003464B
0x1400345e4  test    r14, r14
0x1400345e7  jz      short loc_14003460E
0x1400345e9  cmp     rsi, rdi
0x1400345ec  jb      short loc_14003460E
0x1400345ee  mov     r8, rdi; Size
0x1400345f1  mov     rdx, r14; Src
0x1400345f4  call    memcpy_0
0x1400345f9  add     [rbx], ebp
0x1400345fb  mov     rax, [rbx+8]
0x1400345ff  movsxd  rcx, dword ptr [rbx]
0x140034602  mov     [rax+rcx*2], r15w
0x140034607  mov     eax, 1
0x14003460c  jmp     short loc_140034621
0x14003460e  mov     r8, rsi; Size
0x140034611  xor     edx, edx; Val
0x140034613  call    memset_0
0x140034618  test    r14, r14
0x14003461b  jnz     short loc_14003463A
0x14003461d  jmp     short loc_1400345D6
0x14003461f  xor     eax, eax
0x140034621  mov     rbx, [rsp+38h+arg_0]
0x140034626  mov     rbp, [rsp+38h+arg_8]
0x14003462b  mov     rsi, [rsp+38h+arg_10]
0x140034630  add     rsp, 20h
0x140034634  pop     r15
0x140034636  pop     r14
0x140034638  pop     rdi
0x140034639  retn
0x14003463a  cmp     rsi, rdi
0x14003463d  jnb     short loc_140034651
0x14003463f  call    cs:__imp__errno
0x140034645  mov     dword ptr [rax], 22h ; '"'
0x14003464b  call    cs:__imp__invalid_parameter_noinfo
0x140034651  mov     ecx, 80070057h; int
0x140034656  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
