# ISAPI_REQUEST::MapPath(uchar *,ulong,ulong *,int)

- ea: `0x18000e370`
- end: `0x18000e5f3`
- name: `?MapPath@ISAPI_REQUEST@@UEAAJPEAEKPEAKH@Z`
- size: `643`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *this, unsigned __int16 *, unsigned int, unsigned int *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x18000e370`
- `0x180012482`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000e57b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000e5cf`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000e57b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000e5cf`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000e553`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000e553`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e586`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e591`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e5de`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e5e9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e586`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e591`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e5de`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e5e9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000e41b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000e41b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e45e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e46c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e4e6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e4f4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e55e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e45e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e46c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e4e6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e4f4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e55e`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000e441`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000e4c4`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000e441`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000e4c4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e3d6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e3fc`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e3d6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e3fc`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000e423`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000e423`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000e438`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000e4bb`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000e438`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000e4bb`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000e4a6`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000e4a6`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000e51b`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000e51b`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18000e538`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18000e538`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000e56b`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000e56b`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x18000e5c3`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x18000e5c3`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::MapPath(
        ISAPI_REQUEST *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int *a4,
        int a5)
{
  int v9; // eax
  int v10; // ebx
  BUFFER *Buffer; // rax
  unsigned int Size; // eax
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned int *); // rdi
  unsigned __int16 *Str; // rbx
  unsigned __int16 *v16; // rax
  int v17; // eax
  BUFFER *v18; // rax
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned int *); // rdi
  unsigned __int16 *v21; // rbx
  unsigned __int16 *v22; // rax
  const unsigned __int16 *v23; // rax
  unsigned int v25; // [rsp+30h] [rbp-D0h] BYREF
  ISAPI_REQUEST *v26; // [rsp+38h] [rbp-C8h]
  _BYTE v27[56]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v28[56]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v29[64]; // [rsp+B0h] [rbp-50h] BYREF
  char v30[272]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v31[264]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v32[264]; // [rsp+410h] [rbp+310h] BYREF

  v26 = this;
  memset_0(v31, 0, 0x208u);
  STRU::STRU((STRU *)v28, v31, 0x104u);
  memset_0(v32, 0, 0x208u);
  STRU::STRU((STRU *)v27, v32, 0x104u);
  v25 = 0;
  if ( a5 )
    v9 = STRU::Copy((STRU *)v28, a2);
  else
    v9 = STRU::CopyA((STRU *)v28, (const char *)a2);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_13;
  Buffer = STRU::QueryBuffer((STRU *)v27);
  Size = BUFFER::QuerySize(Buffer);
  v13 = *((_QWORD *)this + 3);
  v25 = Size;
  v14 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned int *))(*(_QWORD *)v13
                                                                                                  + 216LL);
  Str = STRU::QueryStr((STRU *)v27);
  v16 = STRU::QueryStr((STRU *)v28);
  v17 = v14(v13, v16, Str, &v25);
  v10 = v17;
  if ( v17 < 0 )
  {
    if ( v17 != -2147024774 )
      goto LABEL_13;
    v10 = STRU::Resize((STRU *)v27, v25);
    if ( v10 < 0 )
      goto LABEL_13;
    v18 = STRU::QueryBuffer((STRU *)v27);
    v25 = BUFFER::QuerySize(v18);
    v19 = *((_QWORD *)v26 + 3);
    v20 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned int *))(*(_QWORD *)v19 + 216LL);
    v21 = STRU::QueryStr((STRU *)v27);
    v22 = STRU::QueryStr((STRU *)v28);
    v10 = v20(v19, v22, v21, &v25);
    if ( v10 < 0 )
      goto LABEL_13;
  }
  STRU::SyncWithBuffer((STRU *)v27);
  if ( a5 )
  {
    *a4 = a3;
    v10 = STRU::CopyToBuffer((STRU *)v27, a2, a4);
  }
  else
  {
    STRA::STRA((STRA *)v29, v30, 0x104u);
    v23 = STRU::QueryStr((STRU *)v27);
    v10 = STRA::CopyW((STRA *)v29, v23);
    if ( v10 < 0 )
    {
      STRA::~STRA((STRA *)v29);
LABEL_13:
      STRU::~STRU((STRU *)v27);
      STRU::~STRU((STRU *)v28);
      return (unsigned int)v10;
    }
    *a4 = a3;
    v10 = STRA::CopyToBuffer((STRA *)v29, (char *)a2, a4);
    STRA::~STRA((STRA *)v29);
  }
  if ( v10 < 0 )
    goto LABEL_13;
  STRU::~STRU((STRU *)v27);
  STRU::~STRU((STRU *)v28);
  return 0;
}

```

## disassembly

```asm
0x18000e370  push    rbp
0x18000e372  push    rbx
0x18000e373  push    rsi
0x18000e374  push    rdi
0x18000e375  push    r12
0x18000e377  push    r14
0x18000e379  push    r15
0x18000e37b  lea     rbp, [rsp-530h]
0x18000e383  sub     rsp, 630h
0x18000e38a  mov     rax, cs:__security_cookie
0x18000e391  xor     rax, rsp
0x18000e394  mov     [rbp+560h+var_40], rax
0x18000e39b  mov     r12d, r8d
0x18000e39e  mov     [rsp+660h+var_628], rcx
0x18000e3a3  mov     r15, rdx
0x18000e3a6  mov     rdi, rcx
0x18000e3a9  mov     ebx, 208h
0x18000e3ae  lea     rcx, [rbp+560h+var_460]; void *
0x18000e3b5  mov     r8d, ebx; Size
0x18000e3b8  xor     edx, edx; Val
0x18000e3ba  mov     r14, r9
0x18000e3bd  call    memset_0
0x18000e3c2  mov     esi, 104h
0x18000e3c7  lea     rdx, [rbp+560h+var_460]
0x18000e3ce  mov     r8d, esi
0x18000e3d1  lea     rcx, [rsp+660h+var_5E8]
0x18000e3d6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000e3dc  mov     r8d, ebx; Size
0x18000e3df  lea     rcx, [rbp+560h+var_250]; void *
0x18000e3e6  xor     edx, edx; Val
0x18000e3e8  call    memset_0
0x18000e3ed  mov     r8d, esi
0x18000e3f0  lea     rdx, [rbp+560h+var_250]
0x18000e3f7  lea     rcx, [rsp+660h+var_620]
0x18000e3fc  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000e402  cmp     [rbp+560h+arg_20], 0
0x18000e409  lea     rcx, [rsp+660h+var_5E8]
0x18000e40e  mov     [rsp+660h+var_630], 0
0x18000e416  mov     rdx, r15
0x18000e419  jz      short loc_18000E423
0x18000e41b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000e421  jmp     short loc_18000E429
0x18000e423  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18000e429  mov     ebx, eax
0x18000e42b  test    eax, eax
0x18000e42d  js      loc_18000E581
0x18000e433  lea     rcx, [rsp+660h+var_620]
0x18000e438  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x18000e43e  mov     rcx, rax
0x18000e441  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000e447  mov     rsi, [rdi+18h]
0x18000e44b  lea     rcx, [rsp+660h+var_620]
0x18000e450  mov     [rsp+660h+var_630], eax
0x18000e454  mov     rax, [rsi]
0x18000e457  mov     rdi, [rax+0D8h]
0x18000e45e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e464  lea     rcx, [rsp+660h+var_5E8]
0x18000e469  mov     rbx, rax
0x18000e46c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e472  lea     r9, [rsp+660h+var_630]
0x18000e477  mov     r8, rbx
0x18000e47a  mov     rdx, rax
0x18000e47d  mov     rcx, rsi
0x18000e480  mov     rax, rdi
0x18000e483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e488  mov     ebx, eax
0x18000e48a  test    eax, eax
0x18000e48c  jns     loc_18000E516
0x18000e492  cmp     eax, 8007007Ah
0x18000e497  jnz     loc_18000E581
0x18000e49d  mov     edx, [rsp+660h+var_630]
0x18000e4a1  lea     rcx, [rsp+660h+var_620]
0x18000e4a6  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18000e4ac  mov     ebx, eax
0x18000e4ae  test    eax, eax
0x18000e4b0  js      loc_18000E581
0x18000e4b6  lea     rcx, [rsp+660h+var_620]
0x18000e4bb  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x18000e4c1  mov     rcx, rax
0x18000e4c4  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000e4ca  mov     rsi, [rsp+660h+var_628]
0x18000e4cf  lea     rcx, [rsp+660h+var_620]
0x18000e4d4  mov     [rsp+660h+var_630], eax
0x18000e4d8  mov     rsi, [rsi+18h]
0x18000e4dc  mov     rax, [rsi]
0x18000e4df  mov     rdi, [rax+0D8h]
0x18000e4e6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e4ec  lea     rcx, [rsp+660h+var_5E8]
0x18000e4f1  mov     rbx, rax
0x18000e4f4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e4fa  lea     r9, [rsp+660h+var_630]
0x18000e4ff  mov     r8, rbx
0x18000e502  mov     rdx, rax
0x18000e505  mov     rcx, rsi
0x18000e508  mov     rax, rdi
0x18000e50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e510  mov     ebx, eax
0x18000e512  test    eax, eax
0x18000e514  js      short loc_18000E581
0x18000e516  lea     rcx, [rsp+660h+var_620]
0x18000e51b  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000e521  cmp     [rbp+560h+arg_20], 0
0x18000e528  jz      short loc_18000E545
0x18000e52a  mov     r8, r14
0x18000e52d  mov     [r14], r12d
0x18000e530  mov     rdx, r15
0x18000e533  lea     rcx, [rsp+660h+var_620]
0x18000e538  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x18000e53e  mov     ebx, eax
0x18000e540  jmp     loc_18000E5D5
0x18000e545  mov     r8d, 104h
0x18000e54b  lea     rdx, [rbp+560h+var_570]
0x18000e54f  lea     rcx, [rbp+560h+var_5B0]
0x18000e553  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000e559  lea     rcx, [rsp+660h+var_620]
0x18000e55e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e564  mov     rdx, rax
0x18000e567  lea     rcx, [rbp+560h+var_5B0]
0x18000e56b  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18000e571  lea     rcx, [rbp+560h+var_5B0]
0x18000e575  mov     ebx, eax
0x18000e577  test    eax, eax
0x18000e579  jns     short loc_18000E5BA
0x18000e57b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000e581  lea     rcx, [rsp+660h+var_620]
0x18000e586  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e58c  lea     rcx, [rsp+660h+var_5E8]
0x18000e591  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e597  mov     eax, ebx
0x18000e599  mov     rcx, [rbp+560h+var_40]
0x18000e5a0  xor     rcx, rsp; StackCookie
0x18000e5a3  call    __security_check_cookie
0x18000e5a8  add     rsp, 630h
0x18000e5af  pop     r15
0x18000e5b1  pop     r14
0x18000e5b3  pop     r12
0x18000e5b5  pop     rdi
0x18000e5b6  pop     rsi
0x18000e5b7  pop     rbx
0x18000e5b8  pop     rbp
0x18000e5b9  retn
0x18000e5ba  mov     r8, r14
0x18000e5bd  mov     [r14], r12d
0x18000e5c0  mov     rdx, r15
0x18000e5c3  call    cs:__imp_?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z; STRA::CopyToBuffer(char *,ulong *)
0x18000e5c9  lea     rcx, [rbp+560h+var_5B0]
0x18000e5cd  mov     ebx, eax
0x18000e5cf  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000e5d5  test    ebx, ebx
0x18000e5d7  js      short loc_18000E581
0x18000e5d9  lea     rcx, [rsp+660h+var_620]
0x18000e5de  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e5e4  lea     rcx, [rsp+660h+var_5E8]
0x18000e5e9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e5ef  xor     eax, eax
0x18000e5f1  jmp     short loc_18000E599
```
