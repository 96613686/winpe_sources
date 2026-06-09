# FTP_SESSION::WriteResponseHelper(ulong,char const *,char const *,char *)

- ea: `0x180036ebc`
- end: `0x180037226`
- name: `?WriteResponseHelper@FTP_SESSION@@QEAAJKPEBD0PEAD@Z`
- size: `874`
- prototype: `int(FTP_SESSION *__hidden this, unsigned int, const char *, const char *, char *)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180036e90`
- `0x18003e350`
- `0x18003e384`
- `0x18003e3c8`
- `0x18003e564`
- `0x18003e708`
- `0x18003e980`

## callees

- `0x180036ebc`
- `0x180041d08`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!strstr` at `0x180037037`
- `msvcrt!strstr` at `0x180037037`
- `msvcrt!_vsnprintf` at `0x180036f93`
- `msvcrt!_vsnprintf` at `0x180036f93`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180036f17`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180036f2c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180036f17`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180036f2c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800371e8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800371f4`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800371e8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800371f4`
- `iisutil!?SyncWithBuffer@STRA@@QEAAXXZ` at `0x180037023`
- `iisutil!?SyncWithBuffer@STRA@@QEAAXXZ` at `0x180037023`
- `iisutil!?Resize@STRA@@QEAAJK@Z` at `0x180036fd4`
- `iisutil!?Resize@STRA@@QEAAJK@Z` at `0x180036fd4`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18003712b`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18003712b`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180037084`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800370ae`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800370e0`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180037101`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18003711d`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180037084`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800370ae`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800370e0`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180037101`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18003711d`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180037003`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180037068`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180037003`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180037068`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FTP_SESSION::WriteResponseHelper(
        FTP_SESSION *this,
        char a2,
        const char *a3,
        const char *a4,
        va_list ArgList)
{
  const char *v6; // rbx
  unsigned int v8; // edx
  char *v9; // rsi
  size_t v10; // rdi
  int v11; // eax
  int v12; // ebx
  int v13; // r15d
  char *v14; // rsi
  char *v15; // rax
  char *v16; // rdi
  int v17; // r14d
  BOOL v18; // r12d
  const char *v19; // rdx
  int v20; // eax
  unsigned int v21; // edi
  unsigned int v22; // esi
  __int64 v23; // rbx
  int v26; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v27; // [rsp+30h] [rbp-D0h]
  int v28; // [rsp+38h] [rbp-C8h]
  __int64 v29; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v30; // [rsp+48h] [rbp-B8h]
  void (__fastcall *v31)(__int64, _QWORD); // [rsp+50h] [rbp-B0h]
  FTP_SESSION *v32; // [rsp+58h] [rbp-A8h]
  _BYTE v33[32]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+80h] [rbp-80h]
  unsigned int v35; // [rsp+88h] [rbp-78h]
  unsigned int v36; // [rsp+90h] [rbp-70h]
  _BYTE v37[32]; // [rsp+98h] [rbp-68h] BYREF
  char *Buffer; // [rsp+B8h] [rbp-48h]
  unsigned int v39; // [rsp+C0h] [rbp-40h]
  char v40[256]; // [rsp+D0h] [rbp-30h] BYREF
  char v41[256]; // [rsp+1D0h] [rbp+D0h] BYREF

  v6 = a3;
  v32 = this;
  STRA::STRA((STRA *)v33, v40, 0x100u);
  STRA::STRA((STRA *)v37, v41, 0x100u);
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v26 = 1396855620;
  if ( (a2 & 8) == 0 && ArgList )
  {
    while ( 1 )
    {
      v8 = v39;
      v9 = Buffer;
      if ( v39 )
      {
        if ( v39 > 0x7FFFFFFFuLL )
        {
          *Buffer = 0;
          v12 = -2147024809;
          v8 = v39;
          goto LABEL_12;
        }
        v10 = v39 - 1LL;
        v11 = _vsnprintf(Buffer, v10, a4, ArgList);
        if ( v11 < 0 || v11 > v10 )
        {
          v9[v10] = 0;
          v12 = -2147024774;
        }
        else
        {
          v12 = 0;
          if ( v11 == v10 )
            v9[v10] = 0;
        }
        v8 = v39;
      }
      else
      {
        v12 = -2147024809;
      }
      if ( v12 >= 0 )
        goto LABEL_19;
LABEL_12:
      if ( 2 * v8 <= 0xFFFF )
      {
        v12 = STRA::Resize((STRA *)v37, 2 * v8);
        if ( v12 >= 0 )
          continue;
      }
      goto LABEL_45;
    }
  }
  if ( a4 )
  {
    v12 = STRA::Copy((STRA *)v37, a4);
    if ( v12 < 0 )
      goto LABEL_45;
LABEL_19:
    v6 = a3;
  }
  v13 = a2 & 1;
  STRA::SyncWithBuffer((STRA *)v37);
  v14 = Buffer;
  while ( 1 )
  {
    v15 = strstr(v14, "\r\n");
    v16 = v15;
    if ( v15 )
    {
      v16 = v15 + 2;
      v17 = 1;
      v18 = v15[2] == 0;
      if ( v15[2] )
        goto LABEL_23;
    }
    else
    {
      v17 = 0;
      v18 = 1;
    }
    if ( (a2 & 2) != 0 )
    {
      v12 = STRA::Append((STRA *)v33, v6);
      if ( v12 < 0 )
        goto LABEL_45;
      v19 = " ";
LABEL_33:
      v12 = STRA::Append((STRA *)v33, v19);
      if ( v12 < 0 )
        goto LABEL_45;
      goto LABEL_34;
    }
LABEL_23:
    if ( !v13 )
    {
      v19 = " ";
      if ( (a2 & 0x10) == 0 )
        v19 = "    ";
      goto LABEL_33;
    }
    v12 = STRA::Copy((STRA *)v33, v6);
    if ( v12 < 0 )
      goto LABEL_45;
    v12 = STRA::Append((STRA *)v33, "-");
    if ( v12 < 0 )
      goto LABEL_45;
    v13 = 0;
LABEL_34:
    if ( ((v17 ^ 1) & v18) != 0 )
    {
      v12 = STRA::Append((STRA *)v33, v14);
      if ( v12 < 0 )
        goto LABEL_45;
      v20 = STRA::Append((STRA *)v33, "\r\n");
    }
    else
    {
      v20 = STRA::Append((STRA *)v33, v14, (_DWORD)v16 - (_DWORD)v14);
    }
    v12 = v20;
    if ( v20 < 0 )
      goto LABEL_45;
    v14 = v16;
    if ( !v16 || !*v16 )
      break;
    v6 = a3;
  }
  v21 = v35;
  v22 = v36;
  v23 = v34;
  if ( v31 )
    v31(v27, HIDWORD(v30));
  v27 = v23;
  v28 = 0;
  v29 = v23;
  v30 = __PAIR64__(v21, v22);
  v31 = 0;
  v12 = FTP_CONTROL_CHANNEL::SyncSend((FTP_SESSION *)((char *)v32 + 1064), (struct DATA_STREAM_BUFFER *)&v26, a2 & 2);
LABEL_45:
  if ( v31 )
  {
    v31(v27, HIDWORD(v30));
    v31 = 0;
    v27 = 0;
  }
  v26 = 1935831908;
  STRA::~STRA((STRA *)v37);
  STRA::~STRA((STRA *)v33);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180036ebc  mov     [rsp-8+arg_8], rbx
0x180036ec1  push    rbp
0x180036ec2  push    rsi
0x180036ec3  push    rdi
0x180036ec4  push    r12
0x180036ec6  push    r13
0x180036ec8  push    r14
0x180036eca  push    r15
0x180036ecc  lea     rbp, [rsp-1E0h]
0x180036ed4  sub     rsp, 2E0h
0x180036edb  mov     rax, cs:__security_cookie
0x180036ee2  xor     rax, rsp
0x180036ee5  mov     [rbp+210h+var_40], rax
0x180036eec  mov     r14, r9
0x180036eef  mov     rbx, r8
0x180036ef2  mov     [rsp+310h+var_2F0], rbx
0x180036ef7  mov     r13d, edx
0x180036efa  mov     [rsp+310h+var_2B8], rcx
0x180036eff  mov     r15, [rbp+210h+ArgList]
0x180036f06  mov     edi, 100h
0x180036f0b  mov     r8d, edi
0x180036f0e  lea     rdx, [rbp+210h+var_240]
0x180036f12  lea     rcx, [rsp+310h+var_2B0]
0x180036f17  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180036f1d  nop
0x180036f1e  mov     r8d, edi
0x180036f21  lea     rdx, [rbp+210h+var_140]
0x180036f28  lea     rcx, [rbp+210h+var_278]
0x180036f2c  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180036f32  nop
0x180036f33  xor     eax, eax
0x180036f35  mov     [rsp+310h+var_2E0], rax
0x180036f3a  mov     [rsp+310h+var_2D8], eax
0x180036f3e  mov     [rsp+310h+var_2D0], rax
0x180036f43  mov     [rsp+310h+var_2C8], rax
0x180036f48  mov     [rsp+310h+var_2C0], rax
0x180036f4d  mov     [rsp+310h+var_2E8], 53425344h
0x180036f55  test    r13b, 8
0x180036f59  jnz     loc_180036FF7
0x180036f5f  test    r15, r15
0x180036f62  jz      loc_180036FF7
0x180036f68  mov     r12d, 80070057h
0x180036f6e  mov     edx, [rbp+210h+var_250]
0x180036f71  mov     eax, edx
0x180036f73  mov     rsi, [rbp+210h+Buffer]
0x180036f77  test    edx, edx
0x180036f79  jz      short loc_180036FE5
0x180036f7b  cmp     rax, 7FFFFFFFh
0x180036f81  ja      short loc_180036FEC
0x180036f83  lea     rdi, [rdx-1]
0x180036f87  mov     r9, r15; ArgList
0x180036f8a  mov     r8, r14; Format
0x180036f8d  mov     rdx, rdi; BufferCount
0x180036f90  mov     rcx, rsi; Buffer
0x180036f93  call    cs:__imp__vsnprintf
0x180036f99  test    eax, eax
0x180036f9b  js      short loc_180036FB0
0x180036f9d  cdqe
0x180036f9f  cmp     rax, rdi
0x180036fa2  ja      short loc_180036FB0
0x180036fa4  xor     ebx, ebx
0x180036fa6  cmp     rax, rdi
0x180036fa9  jnz     short loc_180036FB9
0x180036fab  mov     [rdi+rsi], bl
0x180036fae  jmp     short loc_180036FB9
0x180036fb0  mov     byte ptr [rdi+rsi], 0
0x180036fb4  mov     ebx, 8007007Ah
0x180036fb9  mov     edx, [rbp+210h+var_250]
0x180036fbc  test    ebx, ebx
0x180036fbe  jns     short loc_180037013
0x180036fc0  lea     eax, [rdx+rdx]
0x180036fc3  cmp     eax, 0FFFFh
0x180036fc8  ja      loc_1800371B2
0x180036fce  add     edx, edx
0x180036fd0  lea     rcx, [rbp+210h+var_278]
0x180036fd4  call    cs:__imp_?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x180036fda  mov     ebx, eax
0x180036fdc  test    eax, eax
0x180036fde  jns     short loc_180036F6E
0x180036fe0  jmp     loc_1800371B2
0x180036fe5  mov     ebx, r12d
0x180036fe8  test    edx, edx
0x180036fea  jz      short loc_180036FBC
0x180036fec  mov     byte ptr [rsi], 0
0x180036fef  mov     ebx, r12d
0x180036ff2  mov     edx, [rbp+210h+var_250]
0x180036ff5  jmp     short loc_180036FC0
0x180036ff7  test    r14, r14
0x180036ffa  jz      short loc_180037018
0x180036ffc  mov     rdx, r14
0x180036fff  lea     rcx, [rbp+210h+var_278]
0x180037003  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180037009  mov     ebx, eax
0x18003700b  test    eax, eax
0x18003700d  js      loc_1800371B2
0x180037013  mov     rbx, [rsp+310h+var_2F0]
0x180037018  mov     r15d, r13d
0x18003701b  and     r15d, 1
0x18003701f  lea     rcx, [rbp+210h+var_278]
0x180037023  call    cs:__imp_?SyncWithBuffer@STRA@@QEAAXXZ; STRA::SyncWithBuffer(void)
0x180037029  mov     rsi, [rbp+210h+Buffer]
0x18003702d  lea     rdx, SubStr; "\r\n"
0x180037034  mov     rcx, rsi; Str
0x180037037  call    cs:__imp_strstr
0x18003703d  mov     rdi, rax
0x180037040  test    rax, rax
0x180037043  jz      short loc_180037099
0x180037045  add     rdi, 2
0x180037049  mov     r14d, 1
0x18003704f  xor     r12d, r12d
0x180037052  cmp     [rdi], r12b
0x180037055  setz    r12b
0x180037059  jz      short loc_1800370A0
0x18003705b  test    r15d, r15d
0x18003705e  jz      short loc_1800370C7
0x180037060  mov     rdx, rbx
0x180037063  lea     rcx, [rsp+310h+var_2B0]
0x180037068  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18003706e  mov     ebx, eax
0x180037070  test    eax, eax
0x180037072  js      loc_1800371B2
0x180037078  lea     rdx, asc_180051D90; "-"
0x18003707f  lea     rcx, [rsp+310h+var_2B0]
0x180037084  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18003708a  mov     ebx, eax
0x18003708c  test    eax, eax
0x18003708e  js      loc_1800371B2
0x180037094  xor     r15d, r15d
0x180037097  jmp     short loc_1800370F0
0x180037099  xor     r14d, r14d
0x18003709c  lea     r12d, [r14+1]
0x1800370a0  test    r13b, 2
0x1800370a4  jz      short loc_18003705B
0x1800370a6  mov     rdx, rbx
0x1800370a9  lea     rcx, [rsp+310h+var_2B0]
0x1800370ae  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x1800370b4  mov     ebx, eax
0x1800370b6  test    eax, eax
0x1800370b8  js      loc_1800371B2
0x1800370be  lea     rdx, asc_180051D8C; " "
0x1800370c5  jmp     short loc_1800370DB
0x1800370c7  test    r13b, 10h
0x1800370cb  lea     rdx, asc_180051D8C; " "
0x1800370d2  jnz     short loc_1800370DB
0x1800370d4  lea     rdx, asc_180053F18; "    "
0x1800370db  lea     rcx, [rsp+310h+var_2B0]
0x1800370e0  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x1800370e6  mov     ebx, eax
0x1800370e8  test    eax, eax
0x1800370ea  js      loc_1800371B2
0x1800370f0  xor     r14d, 1
0x1800370f4  mov     rdx, rsi
0x1800370f7  lea     rcx, [rsp+310h+var_2B0]
0x1800370fc  test    r12d, r14d
0x1800370ff  jz      short loc_180037125
0x180037101  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180037107  mov     ebx, eax
0x180037109  test    eax, eax
0x18003710b  js      loc_1800371B2
0x180037111  lea     rdx, SubStr; "\r\n"
0x180037118  lea     rcx, [rsp+310h+var_2B0]
0x18003711d  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180037123  jmp     short loc_180037131
0x180037125  mov     r8d, edi
0x180037128  sub     r8d, esi
0x18003712b  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180037131  test    eax, eax
0x180037133  mov     ebx, eax
0x180037135  js      short loc_1800371B2
0x180037137  mov     rsi, rdi
0x18003713a  test    rdi, rdi
0x18003713d  jz      short loc_18003714E
0x18003713f  cmp     byte ptr [rdi], 0
0x180037142  jz      short loc_18003714E
0x180037144  mov     rbx, [rsp+310h+var_2F0]
0x180037149  jmp     loc_18003702D
0x18003714e  mov     edi, [rbp+210h+var_288]
0x180037151  mov     esi, [rbp+210h+var_280]
0x180037154  mov     rbx, [rbp+210h+var_290]
0x180037158  mov     rax, [rsp+310h+var_2C0]
0x18003715d  test    rax, rax
0x180037160  jz      short loc_180037170
0x180037162  mov     edx, dword ptr [rsp+310h+var_2C8+4]
0x180037166  mov     rcx, [rsp+310h+var_2E0]
0x18003716b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037170  mov     [rsp+310h+var_2E0], rbx
0x180037175  mov     [rsp+310h+var_2D8], 0
0x18003717d  mov     [rsp+310h+var_2D0], rbx
0x180037182  mov     dword ptr [rsp+310h+var_2C8], esi
0x180037186  mov     dword ptr [rsp+310h+var_2C8+4], edi
0x18003718a  mov     [rsp+310h+var_2C0], 0
0x180037193  and     r13d, 2
0x180037197  mov     rcx, [rsp+310h+var_2B8]
0x18003719c  add     rcx, 428h; this
0x1800371a3  mov     r8d, r13d; int
0x1800371a6  lea     rdx, [rsp+310h+var_2E8]; struct DATA_STREAM_BUFFER *
0x1800371ab  call    ?SyncSend@FTP_CONTROL_CHANNEL@@QEAAJPEAVDATA_STREAM_BUFFER@@H@Z; FTP_CONTROL_CHANNEL::SyncSend(DATA_STREAM_BUFFER *,int)
0x1800371b0  mov     ebx, eax
0x1800371b2  mov     rax, [rsp+310h+var_2C0]
0x1800371b7  test    rax, rax
0x1800371ba  jz      short loc_1800371DC
0x1800371bc  mov     edx, dword ptr [rsp+310h+var_2C8+4]
0x1800371c0  mov     rcx, [rsp+310h+var_2E0]
0x1800371c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371ca  mov     [rsp+310h+var_2C0], 0
0x1800371d3  mov     [rsp+310h+var_2E0], 0
0x1800371dc  mov     [rsp+310h+var_2E8], 73627364h
0x1800371e4  lea     rcx, [rbp+210h+var_278]
0x1800371e8  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800371ee  nop
0x1800371ef  lea     rcx, [rsp+310h+var_2B0]
0x1800371f4  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800371fa  mov     eax, ebx
0x1800371fc  mov     rcx, [rbp+210h+var_40]
0x180037203  xor     rcx, rsp; StackCookie
0x180037206  call    __security_check_cookie
0x18003720b  mov     rbx, [rsp+310h+arg_8]
0x180037213  add     rsp, 2E0h
0x18003721a  pop     r15
0x18003721c  pop     r14
0x18003721e  pop     r13
0x180037220  pop     r12
0x180037222  pop     rdi
0x180037223  pop     rsi
0x180037224  pop     rbp
0x180037225  retn
```
