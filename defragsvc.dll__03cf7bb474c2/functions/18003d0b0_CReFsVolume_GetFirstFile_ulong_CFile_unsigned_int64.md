# CReFsVolume::GetFirstFile(ulong *,_CFile *,unsigned __int64 *)

- ea: `0x18003d0b0`
- end: `0x18003d300`
- name: `?GetFirstFile@CReFsVolume@@UEAAJPEAKPEAU_CFile@@PEA_K@Z`
- size: `592`
- prototype: `__int64 __fastcall(CReFsVolume *__hidden this, unsigned int *, struct _CFile *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180011ac4`
- `0x1800157fc`
- `0x18001913c`
- `0x18001f468`
- `0x18001fed8`
- `0x18001ff18`
- `0x18003d0b0`
- `0x180067b0a`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d245`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d245`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CReFsVolume::GetFirstFile(
        CReFsVolume *this,
        unsigned int *a2,
        struct _CFile *a3,
        unsigned __int64 *a4)
{
  __int64 v8; // rsi
  __int64 v9; // rcx
  struct _CFile *v10; // rax
  __int16 v11; // ax
  int File; // ebx
  CFatVolume *v13; // rcx
  __int64 v14; // rax
  unsigned __int16 v15; // dx
  _BYTE *v16; // rax
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v19; // [rsp+24h] [rbp-DCh]
  __int16 v20; // [rsp+26h] [rbp-DAh]
  LPVOID v21[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct _QUEUED_DIR *v22; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v23; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v24[80]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v25; // [rsp+D0h] [rbp-30h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "CReFsVolume::GetFirstFile", 139, 1);
  v23 = 0;
  memset_0(v24, 0, 0x280u);
  v21[0] = (LPVOID)&qword_18006F470;
  v21[1] = 0;
  if ( a2 )
    *a2 = 0;
  v8 = 16;
  if ( a3 )
  {
    v9 = 16;
    v10 = a3;
    do
    {
      *(_BYTE *)v10 = 0;
      v10 = (struct _CFile *)((char *)v10 + 1);
      --v9;
    }
    while ( v9 );
  }
  if ( a4 )
    *a4 = 0;
  v11 = 149;
  if ( a2 && (v19 = 149, v11 = 150, a4) )
  {
    v18 = 0;
    v19 = 150;
    File = (*(__int64 (__fastcall **)(CReFsVolume *, _BYTE *))(*(_QWORD *)this + 48LL))(this, v24);
    v18 = File;
    v11 = 153;
    if ( File >= 0 )
    {
      v19 = 153;
      *((_QWORD *)this + 130) = 0;
      while ( 1 )
      {
        v14 = *((_QWORD *)this + 129);
        if ( !v14 )
          break;
        v22 = (struct _QUEUED_DIR *)*((_QWORD *)this + 129);
        *((_QWORD *)this + 129) = *(_QWORD *)(v14 + 8);
        CFatVolume::FreeDir(v13, (LPVOID **)&v22);
      }
      File = CBsString::Set((CBsString *)v21, *((const unsigned __int16 **)this + 6));
      v18 = File;
      v11 = 166;
      if ( File >= 0 )
      {
        v19 = 166;
        File = CBsString::Trailing((CBsString *)v21, v15);
        v18 = File;
        v11 = 167;
        if ( File >= 0 )
        {
          v19 = 167;
          v16 = CoTaskMemAlloc(0x10u);
          *((_QWORD *)this + 129) = v16;
          if ( !v16 )
          {
            File = -2147024882;
            v18 = -2147024882;
            v20 = 172;
            goto LABEL_24;
          }
          v18 = 0;
          v19 = 172;
          do
          {
            *v16++ = 0;
            --v8;
          }
          while ( v8 );
          CBsString::Detach((CBsString *)v21, *((unsigned __int16 ***)this + 129));
          File = CReFsVolume::_GetFile(this, a2, a3, &v23);
          v18 = File;
          v11 = 176;
          if ( File >= 0 )
          {
            v19 = 176;
            *a4 = v25;
            goto LABEL_24;
          }
        }
      }
    }
  }
  else
  {
    File = -2147024809;
    v18 = -2147024809;
  }
  v20 = v11;
LABEL_24:
  CBsString::_Release(v21);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18);
  return (unsigned int)File;
}

```

## disassembly

```asm
0x18003d0b0  push    rbp
0x18003d0b2  push    rbx
0x18003d0b3  push    rsi
0x18003d0b4  push    rdi
0x18003d0b5  push    r12
0x18003d0b7  push    r14
0x18003d0b9  push    r15
0x18003d0bb  lea     rbp, [rsp-210h]
0x18003d0c3  sub     rsp, 310h
0x18003d0ca  mov     rax, cs:__security_cookie
0x18003d0d1  xor     rax, rsp
0x18003d0d4  mov     [rbp+240h+var_40], rax
0x18003d0db  mov     r14, r9
0x18003d0de  mov     r12, r8
0x18003d0e1  mov     r15, rdx
0x18003d0e4  mov     rdi, rcx
0x18003d0e7  mov     r9d, 1; unsigned __int16
0x18003d0ed  mov     r8d, 8Bh; unsigned __int16
0x18003d0f3  lea     rdx, aCrefsvolumeGet_9; "CReFsVolume::GetFirstFile"
0x18003d0fa  lea     rcx, [rsp+340h+var_320]; this
0x18003d0ff  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003d104  nop
0x18003d105  mov     [rsp+340h+var_2D0], 0
0x18003d10e  xor     edx, edx; Val
0x18003d110  mov     r8d, 280h; Size
0x18003d116  lea     rcx, [rbp+240h+var_2C0]; void *
0x18003d11a  call    memset_0
0x18003d11f  lea     rax, qword_18006F470
0x18003d126  mov     [rsp+340h+var_2E8], rax
0x18003d12b  mov     [rsp+340h+var_2E0], 0
0x18003d134  test    r15, r15
0x18003d137  jz      short loc_18003D140
0x18003d139  mov     dword ptr [r15], 0
0x18003d140  mov     esi, 10h
0x18003d145  test    r12, r12
0x18003d148  jz      short loc_18003D15B
0x18003d14a  mov     ecx, esi
0x18003d14c  mov     rax, r12
0x18003d14f  mov     byte ptr [rax], 0
0x18003d152  inc     rax
0x18003d155  sub     rcx, 1
0x18003d159  jnz     short loc_18003D14F
0x18003d15b  test    r14, r14
0x18003d15e  jz      short loc_18003D167
0x18003d160  mov     qword ptr [r14], 0
0x18003d167  mov     eax, 95h
0x18003d16c  test    r15, r15
0x18003d16f  jnz     short loc_18003D184
0x18003d171  mov     ebx, 80070057h
0x18003d176  mov     [rsp+340h+var_320], ebx
0x18003d17a  mov     [rsp+340h+var_31A], ax
0x18003d17f  jmp     loc_18003D2C8
0x18003d184  mov     [rsp+340h+var_31C], ax
0x18003d189  mov     eax, 96h
0x18003d18e  test    r14, r14
0x18003d191  jz      short loc_18003D171
0x18003d193  mov     [rsp+340h+var_320], 0
0x18003d19b  mov     [rsp+340h+var_31C], ax
0x18003d1a0  mov     rax, [rdi]
0x18003d1a3  lea     rdx, [rbp+240h+var_2C0]
0x18003d1a7  mov     rcx, rdi
0x18003d1aa  mov     rax, [rax+30h]
0x18003d1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1b3  mov     ebx, eax
0x18003d1b5  mov     [rsp+340h+var_320], eax
0x18003d1b9  test    eax, eax
0x18003d1bb  mov     eax, 99h
0x18003d1c0  js      short loc_18003D17A
0x18003d1c2  mov     [rsp+340h+var_31C], ax
0x18003d1c7  mov     qword ptr [rdi+410h], 0
0x18003d1d2  jmp     short loc_18003D1EE
0x18003d1d4  mov     [rsp+340h+var_2D8], rax
0x18003d1d9  mov     rax, [rax+8]
0x18003d1dd  mov     [rdi+408h], rax
0x18003d1e4  lea     rdx, [rsp+340h+var_2D8]; struct _QUEUED_DIR **
0x18003d1e9  call    ?FreeDir@CFatVolume@@AEAAXPEAPEAU_QUEUED_DIR@@@Z; CFatVolume::FreeDir(_QUEUED_DIR * *)
0x18003d1ee  mov     rax, [rdi+408h]
0x18003d1f5  test    rax, rax
0x18003d1f8  jnz     short loc_18003D1D4
0x18003d1fa  mov     rdx, [rdi+30h]; unsigned __int16 *
0x18003d1fe  lea     rcx, [rsp+340h+var_2E8]; this
0x18003d203  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003d208  mov     ebx, eax
0x18003d20a  mov     [rsp+340h+var_320], eax
0x18003d20e  test    eax, eax
0x18003d210  mov     eax, 0A6h
0x18003d215  js      loc_18003D17A
0x18003d21b  mov     [rsp+340h+var_31C], ax
0x18003d220  lea     rcx, [rsp+340h+var_2E8]; this
0x18003d225  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18003d22a  mov     ebx, eax
0x18003d22c  mov     [rsp+340h+var_320], eax
0x18003d230  test    eax, eax
0x18003d232  mov     eax, 0A7h
0x18003d237  js      loc_18003D17A
0x18003d23d  mov     [rsp+340h+var_31C], ax
0x18003d242  mov     rcx, rsi; cb
0x18003d245  call    cs:__imp_CoTaskMemAlloc
0x18003d24b  mov     [rdi+408h], rax
0x18003d252  mov     ecx, 0ACh
0x18003d257  test    rax, rax
0x18003d25a  jnz     short loc_18003D26C
0x18003d25c  mov     ebx, 8007000Eh
0x18003d261  mov     [rsp+340h+var_320], ebx
0x18003d265  mov     [rsp+340h+var_31A], cx
0x18003d26a  jmp     short loc_18003D2C8
0x18003d26c  mov     [rsp+340h+var_320], 0
0x18003d274  mov     [rsp+340h+var_31C], cx
0x18003d279  mov     byte ptr [rax], 0
0x18003d27c  inc     rax
0x18003d27f  sub     rsi, 1
0x18003d283  jnz     short loc_18003D279
0x18003d285  mov     rdx, [rdi+408h]; unsigned __int16 **
0x18003d28c  lea     rcx, [rsp+340h+var_2E8]; this
0x18003d291  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x18003d296  lea     r9, [rsp+340h+var_2D0]; unsigned __int64 *
0x18003d29b  mov     r8, r12; struct _CFile *
0x18003d29e  mov     rdx, r15; unsigned int *
0x18003d2a1  mov     rcx, rdi; this
0x18003d2a4  call    ?_GetFile@CReFsVolume@@AEAAJPEAKPEAU_CFile@@PEA_K@Z; CReFsVolume::_GetFile(ulong *,_CFile *,unsigned __int64 *)
0x18003d2a9  mov     ebx, eax
0x18003d2ab  mov     [rsp+340h+var_320], eax
0x18003d2af  test    eax, eax
0x18003d2b1  mov     eax, 0B0h
0x18003d2b6  js      loc_18003D17A
0x18003d2bc  mov     [rsp+340h+var_31C], ax
0x18003d2c1  mov     rcx, [rbp+240h+var_270]
0x18003d2c5  mov     [r14], rcx
0x18003d2c8  lea     rcx, [rsp+340h+var_2E8]; this
0x18003d2cd  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003d2d2  nop
0x18003d2d3  lea     rcx, [rsp+340h+var_320]; this
0x18003d2d8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003d2dd  mov     eax, ebx
0x18003d2df  mov     rcx, [rbp+240h+var_40]
0x18003d2e6  xor     rcx, rsp; StackCookie
0x18003d2e9  call    __security_check_cookie
0x18003d2ee  add     rsp, 310h
0x18003d2f5  pop     r15
0x18003d2f7  pop     r14
0x18003d2f9  pop     r12
0x18003d2fb  pop     rdi
0x18003d2fc  pop     rsi
0x18003d2fd  pop     rbx
0x18003d2fe  pop     rbp
0x18003d2ff  retn
```
