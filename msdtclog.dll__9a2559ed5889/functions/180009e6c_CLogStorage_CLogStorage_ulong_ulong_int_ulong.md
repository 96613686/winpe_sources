# CLogStorage::CLogStorage(ulong,ulong,int,ulong)

- ea: `0x180009e6c`
- end: `0x18000a082`
- name: `??0CLogStorage@@QEAA@KKHK@Z`
- size: `534`
- prototype: `CLogStorage *__fastcall(CLogStorage *this, unsigned int, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800065c8`

## callees

- `0x18000130c`
- `0x180001c14`
- `0x180009e6c`
- `0x18000afa8`
- `0x18000d998`
- `0x18000e64c`
- `0x18001266c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180009fc8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180009fc8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009fe8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009fe8`

## string_xrefs

- `0x18000a02a`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
CLogStorage *__fastcall CLogStorage::CLogStorage(CLogStorage *this, unsigned int a2, int a3, int a4, unsigned int a5)
{
  void *v8; // r9
  unsigned __int16 i; // dx
  unsigned int v10; // r8d
  __int16 v11; // r10
  unsigned int v12; // ecx
  char v13; // al
  __int64 v14; // rbp
  __int64 v15; // rax
  bool v16; // cf
  unsigned __int64 v17; // rax
  _QWORD *v18; // rax
  _QWORD *v19; // rdi
  _SYSTEM_INFO SystemInfo; // [rsp+38h] [rbp-60h] BYREF
  int pExceptionObject; // [rsp+B8h] [rbp+20h] BYREF

  pExceptionObject = a4;
  CSemExclusive::CSemExclusive((CLogStorage *)((char *)this + 688), a2);
  v8 = operator new[](0x400u);
  pulCRCTable = v8;
  if ( !v8 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  lpCalcCRC = (unsigned int (*)(unsigned int, unsigned __int8 *, unsigned int *))CalcCRC;
  for ( i = 0; i < 0x100u; ++i )
  {
    v10 = i;
    v11 = 8;
    do
    {
      v12 = v10 >> 1;
      v13 = v10;
      v10 = (v10 >> 1) ^ 0xEDB88320;
      if ( (v13 & 1) == 0 )
        v10 = v12;
      --v11;
    }
    while ( v11 );
    *((_DWORD *)v8 + i) = v10;
  }
  *((_QWORD *)this + 94) = 0;
  v14 = a5;
  v15 = 80LL * a5;
  if ( !is_mul_ok(a5, 0x50u) )
    v15 = -1;
  v16 = __CFADD__(v15, 8);
  v17 = v15 + 8;
  if ( v16 )
    v17 = -1;
  v18 = operator new[](v17);
  if ( v18 )
  {
    *v18 = v14;
    v19 = v18 + 1;
    `eh vector constructor iterator'(
      v18 + 1,
      0x50u,
      (unsigned int)v14,
      (void (*)(void *))CBuffer::CBuffer,
      (void (*)(void *))CBuffer::~CBuffer);
  }
  else
  {
    v19 = 0;
  }
  *((_QWORD *)this + 94) = v19;
  if ( !v19 )
  {
    TraceFile(-2147024882, "E_OUTOFMEMORY", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0xACu);
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  *((_DWORD *)this + 187) = v14;
  *((_DWORD *)this + 186) = 0;
  CLogStorage::_CommonInit(this, a2, 1);
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  *((_DWORD *)this + 11) = SystemInfo.dwAllocationGranularity;
  *((_DWORD *)this + 14) = a3;
  *((_QWORD *)this + 97) = 0;
  GetSystemTimeAsFileTime((LPFILETIME)this + 1);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 20) = -1;
  *((_QWORD *)this + 19) = -1;
  return this;
}

```

## disassembly

```asm
0x180009e6c  mov     rax, rsp
0x180009e6f  mov     [rax+10h], rbx
0x180009e73  mov     [rax+18h], rbp
0x180009e77  mov     [rax+20h], r9d
0x180009e7b  mov     [rax+8], rcx
0x180009e7f  push    rsi
0x180009e80  push    rdi
0x180009e81  push    r13
0x180009e83  push    r14
0x180009e85  push    r15
0x180009e87  sub     rsp, 70h
0x180009e8b  mov     r14d, r8d
0x180009e8e  mov     r15d, edx
0x180009e91  mov     rbx, rcx
0x180009e94  add     rcx, 2B0h; this
0x180009e9b  call    ??0CSemExclusive@@QEAA@K@Z; CSemExclusive::CSemExclusive(ulong)
0x180009ea0  nop
0x180009ea1  mov     ecx, 400h; unsigned __int64
0x180009ea6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009eab  mov     r9, rax
0x180009eae  mov     cs:?pulCRCTable@@3PEAKEA, rax; ulong * pulCRCTable
0x180009eb5  test    rax, rax
0x180009eb8  jz      loc_18000A062
0x180009ebe  lea     rax, ?CalcCRC@@YAKIPEAEPEAK@Z; CalcCRC(uint,uchar *,ulong *)
0x180009ec5  mov     cs:?lpCalcCRC@@3P6AKIPEAEPEAK@ZEA, rax; ulong (*lpCalcCRC)(uint,uchar *,ulong *)
0x180009ecc  xor     edx, edx
0x180009ece  lea     r11d, [rdx+8]
0x180009ed2  lea     r13d, [rdx+1]
0x180009ed6  movzx   r8d, dx
0x180009eda  movzx   r10d, r11w
0x180009ede  mov     ecx, r8d
0x180009ee1  shr     ecx, 1
0x180009ee3  mov     eax, r8d
0x180009ee6  mov     r8d, ecx
0x180009ee9  xor     r8d, 0EDB88320h
0x180009ef0  test    r13b, al
0x180009ef3  cmovz   r8d, ecx
0x180009ef7  mov     eax, 0FFFFh
0x180009efc  add     r10w, ax
0x180009f00  jnz     short loc_180009EDE
0x180009f02  movzx   eax, dx
0x180009f05  mov     [r9+rax*4], r8d
0x180009f09  add     dx, r13w
0x180009f0d  mov     eax, 100h
0x180009f12  cmp     dx, ax
0x180009f15  jb      short loc_180009ED6
0x180009f17  mov     qword ptr [rbx+2F0h], 0
0x180009f22  mov     ebp, [rsp+98h+arg_20]
0x180009f29  mov     eax, 50h ; 'P'
0x180009f2e  mul     rbp
0x180009f31  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180009f38  cmovb   rax, rcx
0x180009f3c  add     rax, r11
0x180009f3f  cmovb   rax, rcx
0x180009f43  mov     rcx, rax; unsigned __int64
0x180009f46  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009f4b  mov     [rsp+98h+var_68], rax
0x180009f50  test    rax, rax
0x180009f53  jz      short loc_180009F81
0x180009f55  mov     [rax], rbp
0x180009f58  lea     rdi, [rax+8]
0x180009f5c  lea     rax, ??1CBuffer@@QEAA@XZ; CBuffer::~CBuffer(void)
0x180009f63  mov     [rsp+98h+var_78], rax; void (*)(void *)
0x180009f68  lea     r9, ??0CBuffer@@QEAA@XZ; void (*)(void *)
0x180009f6f  mov     r8d, ebp; unsigned __int64
0x180009f72  mov     edx, 50h ; 'P'; unsigned __int64
0x180009f77  mov     rcx, rdi; void *
0x180009f7a  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180009f7f  jmp     short loc_180009F83
0x180009f81  xor     edi, edi
0x180009f83  mov     [rbx+2F0h], rdi
0x180009f8a  test    rdi, rdi
0x180009f8d  jz      loc_18000A024
0x180009f93  mov     [rbx+2ECh], ebp
0x180009f99  mov     dword ptr [rbx+2E8h], 0
0x180009fa3  mov     r8d, r13d; int
0x180009fa6  mov     edx, r15d; unsigned int
0x180009fa9  mov     rcx, rbx; this
0x180009fac  call    ?_CommonInit@CLogStorage@@AEAAXKH@Z; CLogStorage::_CommonInit(ulong,int)
0x180009fb1  xorps   xmm0, xmm0
0x180009fb4  movups  xmmword ptr [rsp+98h+SystemInfo], xmm0
0x180009fb9  movups  xmmword ptr [rsp+98h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180009fbe  movups  xmmword ptr [rsp+98h+SystemInfo.dwNumberOfProcessors], xmm0
0x180009fc3  lea     rcx, [rsp+98h+SystemInfo]; lpSystemInfo
0x180009fc8  call    cs:__imp_GetSystemInfo
0x180009fce  mov     eax, [rsp+98h+SystemInfo.dwAllocationGranularity]
0x180009fd2  mov     [rbx+2Ch], eax
0x180009fd5  mov     [rbx+38h], r14d
0x180009fd9  mov     qword ptr [rbx+308h], 0
0x180009fe4  lea     rcx, [rbx+8]; lpSystemTimeAsFileTime
0x180009fe8  call    cs:__imp_GetSystemTimeAsFileTime
0x180009fee  mov     qword ptr [rbx+10h], 0
0x180009ff6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009ffa  mov     [rbx+0A0h], rax
0x18000a001  mov     [rbx+98h], rax
0x18000a008  mov     rax, rbx
0x18000a00b  lea     r11, [rsp+98h+var_28]
0x18000a010  mov     rbx, [r11+38h]
0x18000a014  mov     rbp, [r11+40h]
0x18000a018  mov     rsp, r11
0x18000a01b  pop     r15
0x18000a01d  pop     r14
0x18000a01f  pop     r13
0x18000a021  pop     rdi
0x18000a022  pop     rsi
0x18000a023  retn
0x18000a024  mov     r9d, 0ACh; unsigned int
0x18000a02a  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000a031  lea     rdx, aEOutofmemory; "E_OUTOFMEMORY"
0x18000a038  mov     ecx, 8007000Eh; int
0x18000a03d  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000a042  mov     [rsp+98h+pExceptionObject], 8007000Eh
0x18000a04d  lea     rdx, _TI1J; pThrowInfo
0x18000a054  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000a05c  call    _CxxThrowException_0
0x18000a062  mov     [rsp+98h+pExceptionObject], 8007000Eh
0x18000a06d  lea     rdx, _TI1J; pThrowInfo
0x18000a074  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000a07c  call    _CxxThrowException_0
```
