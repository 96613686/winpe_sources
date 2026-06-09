# CFatVolume::GetFirstFile(ulong *,_CFile *,unsigned __int64 *)

- ea: `0x1800402b0`
- end: `0x180040500`
- name: `?GetFirstFile@CFatVolume@@UEAAJPEAKPEAU_CFile@@PEA_K@Z`
- size: `592`
- prototype: `__int64 __fastcall(CFatVolume *__hidden this, unsigned int *, struct _CFile *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180011ac4`
- `0x1800157fc`
- `0x1800164ac`
- `0x18001913c`
- `0x18001fed8`
- `0x18001ff18`
- `0x1800402b0`
- `0x180067b0a`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040445`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040445`

## pseudocode

```c
__int64 __fastcall CFatVolume::GetFirstFile(
        CFatVolume *this,
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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "CFatVolume::GetFirstFile", 138, 1);
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
  v11 = 148;
  if ( a2 && (v19 = 148, v11 = 149, a4) )
  {
    v18 = 0;
    v19 = 149;
    File = (*(__int64 (__fastcall **)(CFatVolume *, _BYTE *))(*(_QWORD *)this + 48LL))(this, v24);
    v18 = File;
    v11 = 152;
    if ( File >= 0 )
    {
      v19 = 152;
      *((_QWORD *)this + 50) = 0;
      while ( 1 )
      {
        v14 = *((_QWORD *)this + 49);
        if ( !v14 )
          break;
        v22 = (struct _QUEUED_DIR *)*((_QWORD *)this + 49);
        *((_QWORD *)this + 49) = *(_QWORD *)(v14 + 8);
        CFatVolume::FreeDir(v13, (LPVOID **)&v22);
      }
      File = CBsString::Set((CBsString *)v21, *((const unsigned __int16 **)this + 6));
      v18 = File;
      v11 = 165;
      if ( File >= 0 )
      {
        v19 = 165;
        File = CBsString::Trailing((CBsString *)v21, v15);
        v18 = File;
        v11 = 166;
        if ( File >= 0 )
        {
          v19 = 166;
          v16 = CoTaskMemAlloc(0x10u);
          *((_QWORD *)this + 49) = v16;
          if ( !v16 )
          {
            File = -2147024882;
            v18 = -2147024882;
            v20 = 171;
            goto LABEL_24;
          }
          v18 = 0;
          v19 = 171;
          do
          {
            *v16++ = 0;
            --v8;
          }
          while ( v8 );
          CBsString::Detach((CBsString *)v21, *((unsigned __int16 ***)this + 49));
          File = CFatVolume::_GetFile(this, a2, a3, &v23);
          v18 = File;
          v11 = 175;
          if ( File >= 0 )
          {
            v19 = 175;
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
0x1800402b0  push    rbp
0x1800402b2  push    rbx
0x1800402b3  push    rsi
0x1800402b4  push    rdi
0x1800402b5  push    r12
0x1800402b7  push    r14
0x1800402b9  push    r15
0x1800402bb  lea     rbp, [rsp-210h]
0x1800402c3  sub     rsp, 310h
0x1800402ca  mov     rax, cs:__security_cookie
0x1800402d1  xor     rax, rsp
0x1800402d4  mov     [rbp+240h+var_40], rax
0x1800402db  mov     r14, r9
0x1800402de  mov     r12, r8
0x1800402e1  mov     r15, rdx
0x1800402e4  mov     rdi, rcx
0x1800402e7  mov     r9d, 1; unsigned __int16
0x1800402ed  mov     r8d, 8Ah; unsigned __int16
0x1800402f3  lea     rdx, aCfatvolumeGetf_1; "CFatVolume::GetFirstFile"
0x1800402fa  lea     rcx, [rsp+340h+var_320]; this
0x1800402ff  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180040304  nop
0x180040305  mov     [rsp+340h+var_2D0], 0
0x18004030e  xor     edx, edx; Val
0x180040310  mov     r8d, 280h; Size
0x180040316  lea     rcx, [rbp+240h+var_2C0]; void *
0x18004031a  call    memset_0
0x18004031f  lea     rax, qword_18006F470
0x180040326  mov     [rsp+340h+var_2E8], rax
0x18004032b  mov     [rsp+340h+var_2E0], 0
0x180040334  test    r15, r15
0x180040337  jz      short loc_180040340
0x180040339  mov     dword ptr [r15], 0
0x180040340  mov     esi, 10h
0x180040345  test    r12, r12
0x180040348  jz      short loc_18004035B
0x18004034a  mov     ecx, esi
0x18004034c  mov     rax, r12
0x18004034f  mov     byte ptr [rax], 0
0x180040352  inc     rax
0x180040355  sub     rcx, 1
0x180040359  jnz     short loc_18004034F
0x18004035b  test    r14, r14
0x18004035e  jz      short loc_180040367
0x180040360  mov     qword ptr [r14], 0
0x180040367  mov     eax, 94h
0x18004036c  test    r15, r15
0x18004036f  jnz     short loc_180040384
0x180040371  mov     ebx, 80070057h
0x180040376  mov     [rsp+340h+var_320], ebx
0x18004037a  mov     [rsp+340h+var_31A], ax
0x18004037f  jmp     loc_1800404C8
0x180040384  mov     [rsp+340h+var_31C], ax
0x180040389  mov     eax, 95h
0x18004038e  test    r14, r14
0x180040391  jz      short loc_180040371
0x180040393  mov     [rsp+340h+var_320], 0
0x18004039b  mov     [rsp+340h+var_31C], ax
0x1800403a0  mov     rax, [rdi]
0x1800403a3  lea     rdx, [rbp+240h+var_2C0]
0x1800403a7  mov     rcx, rdi
0x1800403aa  mov     rax, [rax+30h]
0x1800403ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403b3  mov     ebx, eax
0x1800403b5  mov     [rsp+340h+var_320], eax
0x1800403b9  test    eax, eax
0x1800403bb  mov     eax, 98h
0x1800403c0  js      short loc_18004037A
0x1800403c2  mov     [rsp+340h+var_31C], ax
0x1800403c7  mov     qword ptr [rdi+190h], 0
0x1800403d2  jmp     short loc_1800403EE
0x1800403d4  mov     [rsp+340h+var_2D8], rax
0x1800403d9  mov     rax, [rax+8]
0x1800403dd  mov     [rdi+188h], rax
0x1800403e4  lea     rdx, [rsp+340h+var_2D8]; struct _QUEUED_DIR **
0x1800403e9  call    ?FreeDir@CFatVolume@@AEAAXPEAPEAU_QUEUED_DIR@@@Z; CFatVolume::FreeDir(_QUEUED_DIR * *)
0x1800403ee  mov     rax, [rdi+188h]
0x1800403f5  test    rax, rax
0x1800403f8  jnz     short loc_1800403D4
0x1800403fa  mov     rdx, [rdi+30h]; unsigned __int16 *
0x1800403fe  lea     rcx, [rsp+340h+var_2E8]; this
0x180040403  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180040408  mov     ebx, eax
0x18004040a  mov     [rsp+340h+var_320], eax
0x18004040e  test    eax, eax
0x180040410  mov     eax, 0A5h
0x180040415  js      loc_18004037A
0x18004041b  mov     [rsp+340h+var_31C], ax
0x180040420  lea     rcx, [rsp+340h+var_2E8]; this
0x180040425  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18004042a  mov     ebx, eax
0x18004042c  mov     [rsp+340h+var_320], eax
0x180040430  test    eax, eax
0x180040432  mov     eax, 0A6h
0x180040437  js      loc_18004037A
0x18004043d  mov     [rsp+340h+var_31C], ax
0x180040442  mov     rcx, rsi; cb
0x180040445  call    cs:__imp_CoTaskMemAlloc
0x18004044b  mov     [rdi+188h], rax
0x180040452  mov     ecx, 0ABh
0x180040457  test    rax, rax
0x18004045a  jnz     short loc_18004046C
0x18004045c  mov     ebx, 8007000Eh
0x180040461  mov     [rsp+340h+var_320], ebx
0x180040465  mov     [rsp+340h+var_31A], cx
0x18004046a  jmp     short loc_1800404C8
0x18004046c  mov     [rsp+340h+var_320], 0
0x180040474  mov     [rsp+340h+var_31C], cx
0x180040479  mov     byte ptr [rax], 0
0x18004047c  inc     rax
0x18004047f  sub     rsi, 1
0x180040483  jnz     short loc_180040479
0x180040485  mov     rdx, [rdi+188h]; unsigned __int16 **
0x18004048c  lea     rcx, [rsp+340h+var_2E8]; this
0x180040491  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x180040496  lea     r9, [rsp+340h+var_2D0]; unsigned __int64 *
0x18004049b  mov     r8, r12; struct _CFile *
0x18004049e  mov     rdx, r15; unsigned int *
0x1800404a1  mov     rcx, rdi; this
0x1800404a4  call    ?_GetFile@CFatVolume@@AEAAJPEAKPEAU_CFile@@PEA_K@Z; CFatVolume::_GetFile(ulong *,_CFile *,unsigned __int64 *)
0x1800404a9  mov     ebx, eax
0x1800404ab  mov     [rsp+340h+var_320], eax
0x1800404af  test    eax, eax
0x1800404b1  mov     eax, 0AFh
0x1800404b6  js      loc_18004037A
0x1800404bc  mov     [rsp+340h+var_31C], ax
0x1800404c1  mov     rcx, [rbp+240h+var_270]
0x1800404c5  mov     [r14], rcx
0x1800404c8  lea     rcx, [rsp+340h+var_2E8]; this
0x1800404cd  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800404d2  nop
0x1800404d3  lea     rcx, [rsp+340h+var_320]; this
0x1800404d8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800404dd  mov     eax, ebx
0x1800404df  mov     rcx, [rbp+240h+var_40]
0x1800404e6  xor     rcx, rsp; StackCookie
0x1800404e9  call    __security_check_cookie
0x1800404ee  add     rsp, 310h
0x1800404f5  pop     r15
0x1800404f7  pop     r14
0x1800404f9  pop     r12
0x1800404fb  pop     rdi
0x1800404fc  pop     rsi
0x1800404fd  pop     rbx
0x1800404fe  pop     rbp
0x1800404ff  retn
```
