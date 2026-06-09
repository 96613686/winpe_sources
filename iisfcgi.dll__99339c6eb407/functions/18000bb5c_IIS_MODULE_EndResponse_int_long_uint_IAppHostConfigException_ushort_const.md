# IIS_MODULE::EndResponse(int,long,uint,IAppHostConfigException *,ushort const *)

- ea: `0x18000bb5c`
- end: `0x18000bd8b`
- name: `?EndResponse@IIS_MODULE@@AEAAXHJIPEAUIAppHostConfigException@@PEBG@Z`
- size: `559`
- prototype: `void __usercall(IIS_MODULE *__hidden this@<rcx>, int@<edx>, int@<r8d>, unsigned int@<r9d>, struct IAppHostConfigException *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18000b380`
- `0x18000bea0`
- `0x18000cb30`
- `0x18000cfa0`
- `0x18000d370`
- `0x18000dbf0`
- `0x18000e3b0`

## callees

- `0x18000bb5c`
- `0x18000bd94`
- `0x18000e058`
- `0x18000edde`
- `0x18000ee10`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bbe0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bbe0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bc23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bc23`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bbd6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bbd6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bd5b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bd5b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000bca7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000bca7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bcb9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bcc9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bcb9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bcc9`

## string_xrefs

- `0x18000bd1f`: `Service Unavailable`

## pseudocode

```c
void __fastcall IIS_MODULE::EndResponse(
        IIS_MODULE *this,
        int a2,
        int a3,
        unsigned int a4,
        struct IAppHostConfigException *a5,
        const unsigned __int16 *a6)
{
  int v9; // edi
  bool v11; // zf
  __int64 v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // rbx
  unsigned __int16 *v15; // rdx
  __int64 v16; // rdx
  const char *v17; // r8
  __int64 v18; // r9
  unsigned __int16 *v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v20; // [rsp+48h] [rbp-B8h] BYREF
  struct IAppHostConfigException *v21; // [rsp+50h] [rbp-B0h]
  _BYTE v22[32]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+78h] [rbp-88h]
  unsigned int v24; // [rsp+88h] [rbp-78h]
  unsigned __int16 v25[128]; // [rsp+90h] [rbp-70h] BYREF

  v21 = a5;
  v9 = 0;
  v19 = 0;
  v20 = 0;
  memset_0(v25, 0, sizeof(v25));
  STRU::STRU((STRU *)v22, v25, 0x80u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  *((_DWORD *)this + 25) = a2;
  *((_DWORD *)this + 26) = a3;
  if ( a3 >= 0 )
    *((_DWORD *)this + 26) = -2147467259;
  if ( !*((_DWORD *)this + 22) )
  {
    v11 = *((_DWORD *)this + 23) == 0;
    v9 = 1;
    *((_DWORD *)this + 22) = 1;
    if ( !v11 )
      *((_DWORD *)this + 24) = 1;
    IIS_MODULE::RaiseTraceEvents(this, a4, a3);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( !*((_DWORD *)this + 23) && v9 )
  {
    v12 = *((_QWORD *)this + 21);
    *((_QWORD *)this + 21) = 0;
    if ( a2 )
    {
      v13 = 0;
    }
    else
    {
      if ( a4 && (int)IIS_MODULE::GetString(this, a4, (const unsigned __int16 **)&v19, &v20) < 0 )
        v19 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 32LL))(v12);
      if ( v14 )
      {
        v15 = v19;
        if ( v19 )
        {
          if ( a6 )
          {
            STRU::Copy((STRU *)v22, a6);
            STRU::Append((STRU *)v22, L" - ");
            v15 = v19;
          }
          if ( (int)STRU::Append((STRU *)v22, v15) >= 0 )
            (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v14 + 192LL))(v14, v23, v24, 1);
        }
      }
      if ( a4 == 200001 )
      {
        v16 = 503;
        v17 = "Service Unavailable";
        v18 = 4;
      }
      else
      {
        v18 = 0;
        v17 = "Internal Server Error";
        v16 = 500;
      }
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, struct IAppHostConfigException *, _DWORD))(*(_QWORD *)v14 + 24LL))(
        v14,
        v16,
        v17,
        v18,
        a3,
        v21,
        0);
      v13 = 2;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 64LL))(v12, v13);
  }
  STRU::~STRU((STRU *)v22);
}

```

## disassembly

```asm
0x18000bb5c  mov     [rsp-8+arg_8], rbx
0x18000bb61  push    rbp
0x18000bb62  push    rsi
0x18000bb63  push    rdi
0x18000bb64  push    r12
0x18000bb66  push    r13
0x18000bb68  push    r14
0x18000bb6a  push    r15
0x18000bb6c  lea     rbp, [rsp-0A0h]
0x18000bb74  sub     rsp, 1A0h
0x18000bb7b  mov     rax, cs:__security_cookie
0x18000bb82  xor     rax, rsp
0x18000bb85  mov     [rbp+0D0h+var_40], rax
0x18000bb8c  mov     rax, [rbp+0D0h+arg_20]
0x18000bb93  mov     r14d, r8d
0x18000bb96  mov     r15, [rbp+0D0h+arg_28]
0x18000bb9d  mov     r13d, edx
0x18000bba0  mov     rbx, rcx
0x18000bba3  mov     [rsp+1D0h+var_180], rax
0x18000bba8  xor     edi, edi
0x18000bbaa  lea     rcx, [rbp+0D0h+var_140]; void *
0x18000bbae  xor     edx, edx; Val
0x18000bbb0  mov     [rsp+1D0h+var_190], rdi
0x18000bbb5  mov     r8d, 100h; Size
0x18000bbbb  mov     [rsp+1D0h+var_188], edi
0x18000bbbf  mov     esi, r9d
0x18000bbc2  call    memset_0
0x18000bbc7  mov     r8d, 80h
0x18000bbcd  lea     rdx, [rbp+0D0h+var_140]
0x18000bbd1  lea     rcx, [rsp+1D0h+var_178]
0x18000bbd6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000bbdc  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000bbe0  call    cs:__imp_EnterCriticalSection
0x18000bbe6  mov     [rbx+64h], r13d
0x18000bbea  mov     [rbx+68h], r14d
0x18000bbee  test    r14d, r14d
0x18000bbf1  js      short loc_18000BBFA
0x18000bbf3  mov     dword ptr [rbx+68h], 80004005h
0x18000bbfa  mov     eax, 1
0x18000bbff  cmp     [rbx+58h], edi
0x18000bc02  jnz     short loc_18000BC1F
0x18000bc04  cmp     dword ptr [rbx+5Ch], 0
0x18000bc08  mov     edi, eax
0x18000bc0a  mov     [rbx+58h], eax
0x18000bc0d  jz      short loc_18000BC12
0x18000bc0f  mov     [rbx+60h], eax
0x18000bc12  mov     r8d, r14d; int
0x18000bc15  mov     edx, esi; unsigned int
0x18000bc17  mov     rcx, rbx; this
0x18000bc1a  call    ?RaiseTraceEvents@IIS_MODULE@@AEAAXIJ@Z; IIS_MODULE::RaiseTraceEvents(uint,long)
0x18000bc1f  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000bc23  call    cs:__imp_LeaveCriticalSection
0x18000bc29  xor     r12d, r12d
0x18000bc2c  cmp     [rbx+5Ch], r12d
0x18000bc30  jnz     loc_18000BD56
0x18000bc36  test    edi, edi
0x18000bc38  jz      loc_18000BD56
0x18000bc3e  mov     rdi, [rbx+0A8h]
0x18000bc45  mov     [rbx+0A8h], r12
0x18000bc4c  test    r13d, r13d
0x18000bc4f  jz      short loc_18000BC58
0x18000bc51  xor     edx, edx
0x18000bc53  jmp     loc_18000BD47
0x18000bc58  test    esi, esi
0x18000bc5a  jz      short loc_18000BC79
0x18000bc5c  lea     r9, [rsp+1D0h+var_188]; unsigned int *
0x18000bc61  mov     edx, esi; unsigned int
0x18000bc63  lea     r8, [rsp+1D0h+var_190]; unsigned __int16 **
0x18000bc68  mov     rcx, rbx; this
0x18000bc6b  call    ?GetString@IIS_MODULE@@AEAAJIPEAPEBGPEAK@Z; IIS_MODULE::GetString(uint,ushort const * *,ulong *)
0x18000bc70  test    eax, eax
0x18000bc72  jns     short loc_18000BC79
0x18000bc74  mov     [rsp+1D0h+var_190], r12
0x18000bc79  mov     rax, [rdi]
0x18000bc7c  mov     rcx, rdi
0x18000bc7f  mov     rax, [rax+20h]
0x18000bc83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc88  mov     rbx, rax
0x18000bc8b  test    rax, rax
0x18000bc8e  jz      short loc_18000BCF4
0x18000bc90  mov     rdx, [rsp+1D0h+var_190]
0x18000bc95  test    rdx, rdx
0x18000bc98  jz      short loc_18000BCF4
0x18000bc9a  test    r15, r15
0x18000bc9d  jz      short loc_18000BCC4
0x18000bc9f  mov     rdx, r15
0x18000bca2  lea     rcx, [rsp+1D0h+var_178]
0x18000bca7  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000bcad  lea     rdx, asc_180012B98; " - "
0x18000bcb4  lea     rcx, [rsp+1D0h+var_178]
0x18000bcb9  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000bcbf  mov     rdx, [rsp+1D0h+var_190]
0x18000bcc4  lea     rcx, [rsp+1D0h+var_178]
0x18000bcc9  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000bccf  test    eax, eax
0x18000bcd1  js      short loc_18000BCF4
0x18000bcd3  mov     rax, [rbx]
0x18000bcd6  mov     r9d, 1
0x18000bcdc  mov     r8d, [rbp+0D0h+var_148]
0x18000bce0  mov     rcx, rbx
0x18000bce3  mov     rdx, [rsp+1D0h+var_158]
0x18000bce8  mov     rax, [rax+0C0h]
0x18000bcef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcf4  mov     rcx, [rsp+1D0h+var_180]
0x18000bcf9  mov     rax, [rbx]
0x18000bcfc  mov     [rsp+1D0h+var_1A0], r12d
0x18000bd01  mov     [rsp+1D0h+var_1A8], rcx
0x18000bd06  mov     rcx, rbx
0x18000bd09  mov     [rsp+1D0h+var_1B0], r14d
0x18000bd0e  mov     rax, [rax+18h]
0x18000bd12  cmp     esi, 30D41h
0x18000bd18  jnz     short loc_18000BD2E
0x18000bd1a  mov     edx, 1F7h
0x18000bd1f  lea     r8, aServiceUnavail; "Service Unavailable"
0x18000bd26  mov     r9d, 4
0x18000bd2c  jmp     short loc_18000BD3D
0x18000bd2e  xor     r9d, r9d
0x18000bd31  lea     r8, aInternalServer; "Internal Server Error"
0x18000bd38  mov     edx, 1F4h
0x18000bd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd42  mov     edx, 2
0x18000bd47  mov     rax, [rdi]
0x18000bd4a  mov     rcx, rdi
0x18000bd4d  mov     rax, [rax+40h]
0x18000bd51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd56  lea     rcx, [rsp+1D0h+var_178]
0x18000bd5b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000bd61  mov     rcx, [rbp+0D0h+var_40]
0x18000bd68  xor     rcx, rsp; StackCookie
0x18000bd6b  call    __security_check_cookie
0x18000bd70  mov     rbx, [rsp+1D0h+arg_8]
0x18000bd78  add     rsp, 1A0h
0x18000bd7f  pop     r15
0x18000bd81  pop     r14
0x18000bd83  pop     r13
0x18000bd85  pop     r12
0x18000bd87  pop     rdi
0x18000bd88  pop     rsi
0x18000bd89  pop     rbp
0x18000bd8a  retn
```
