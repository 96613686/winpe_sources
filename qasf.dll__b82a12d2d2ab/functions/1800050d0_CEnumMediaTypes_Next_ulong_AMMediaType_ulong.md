# CEnumMediaTypes::Next(ulong,_AMMediaType * *,ulong *)

- ea: `0x1800050d0`
- end: `0x18000524f`
- name: `?Next@CEnumMediaTypes@@UEAAJKPEAPEAU_AMMediaType@@PEAK@Z`
- size: `383`
- prototype: `__int64 __fastcall(CEnumMediaTypes *__hidden this, unsigned int, struct _AMMediaType **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180001460`
- `0x180001cfc`
- `0x1800050d0`
- `0x180007210`
- `0x18001f010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000518c`
- `ole32!CoTaskMemAlloc` at `0x18000518c`

## pseudocode

```c
__int64 __fastcall CEnumMediaTypes::Next(
        CEnumMediaTypes *this,
        unsigned int a2,
        struct _AMMediaType **a3,
        unsigned int *a4)
{
  struct _AMMediaType **v5; // rsi
  unsigned int v9; // r14d
  __int64 v10; // rdx
  __int64 *v11; // rcx
  __int64 v12; // rax
  struct _AMMediaType *v13; // rax
  struct _AMMediaType v14; // [rsp+20h] [rbp-39h] BYREF

  v5 = a3;
  if ( !a3 )
    return 2147500035LL;
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 32LL))(*((_QWORD *)this + 2)) != *((_DWORD *)this + 6) )
    return 2147746307LL;
  if ( a4 )
  {
    *a4 = 0;
  }
  else if ( a2 > 1 )
  {
    return 2147942487LL;
  }
  v9 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      memset_0(&v14, 0, sizeof(v14));
      v10 = *((unsigned int *)this + 2);
      v11 = (__int64 *)*((_QWORD *)this + 2);
      v14.lSampleSize = 1;
      v14.bFixedSizeSamples = 1;
      v12 = *v11;
      *((_DWORD *)this + 2) = v10 + 1;
      if ( (*(unsigned int (__fastcall **)(__int64 *, __int64, struct _AMMediaType *))(v12 + 104))(v11, v10, &v14) )
        break;
      v13 = (struct _AMMediaType *)CoTaskMemAlloc(0x58u);
      *v5 = v13;
      if ( !v13 )
        break;
      ++v5;
      *v13 = v14;
      ++v9;
      v14.pbFormat = 0;
      v14.cbFormat = 0;
      v14.pUnk = 0;
      FreeMediaType(&v14);
      if ( !--a2 )
        goto LABEL_14;
    }
    FreeMediaType(&v14);
  }
LABEL_14:
  if ( a4 )
    *a4 = v9;
  return a2 != 0;
}

```

## disassembly

```asm
0x1800050d0  mov     [rsp-8+arg_8], rbx
0x1800050d5  push    rbp
0x1800050d6  push    rsi
0x1800050d7  push    rdi
0x1800050d8  push    r14
0x1800050da  push    r15
0x1800050dc  lea     rbp, [rsp-37h]
0x1800050e1  sub     rsp, 90h
0x1800050e8  mov     rax, cs:__security_cookie
0x1800050ef  xor     rax, rsp
0x1800050f2  mov     [rbp+57h+var_30], rax
0x1800050f6  mov     rdi, r9
0x1800050f9  mov     rsi, r8
0x1800050fc  mov     ebx, edx
0x1800050fe  mov     r15, rcx
0x180005101  test    r8, r8
0x180005104  jnz     short loc_180005110
0x180005106  mov     eax, 80004003h
0x18000510b  jmp     loc_18000522C
0x180005110  mov     rcx, [rcx+10h]
0x180005114  mov     rax, [rcx]
0x180005117  mov     rax, [rax+20h]
0x18000511b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005120  cmp     eax, [r15+18h]
0x180005124  jnz     loc_180005227
0x18000512a  test    rdi, rdi
0x18000512d  jz      loc_1800051FD
0x180005133  mov     dword ptr [rdi], 0
0x180005139  xor     r14d, r14d
0x18000513c  test    ebx, ebx
0x18000513e  jz      loc_180005216
0x180005144  xor     edx, edx; Val
0x180005146  lea     rcx, [rbp+57h+var_90]; void *
0x18000514a  lea     r8d, [rdx+58h]; Size
0x18000514e  call    memset_0
0x180005153  mov     edx, [r15+8]
0x180005157  mov     rcx, [r15+10h]
0x18000515b  mov     [rbp+57h+var_90.lSampleSize], 1
0x180005162  mov     [rbp+57h+var_90.bFixedSizeSamples], 1
0x180005169  lea     r8d, [rdx+1]
0x18000516d  mov     rax, [rcx]
0x180005170  mov     [r15+8], r8d
0x180005174  lea     r8, [rbp+57h+var_90]
0x180005178  mov     rax, [rax+68h]
0x18000517c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005181  test    eax, eax
0x180005183  jnz     loc_18000520D
0x180005189  lea     ecx, [rax+58h]; cb
0x18000518c  call    cs:__imp_CoTaskMemAlloc
0x180005192  mov     [rsi], rax
0x180005195  lea     rcx, [rbp+57h+var_90]; struct _AMMediaType *
0x180005199  test    rax, rax
0x18000519c  jz      short loc_180005211
0x18000519e  movaps  xmm0, xmmword ptr [rbp+57h+var_90.majortype.Data1]
0x1800051a2  add     rsi, 8
0x1800051a6  movups  xmmword ptr [rax], xmm0
0x1800051a9  inc     r14d
0x1800051ac  movaps  xmm1, xmmword ptr [rbp+57h+var_90.subtype.Data1]
0x1800051b0  movups  xmmword ptr [rax+10h], xmm1
0x1800051b4  movaps  xmm0, xmmword ptr [rbp+57h+var_90.bFixedSizeSamples]
0x1800051b8  movups  xmmword ptr [rax+20h], xmm0
0x1800051bc  movaps  xmm1, xmmword ptr [rbp+57h+var_90.formattype.Data2]
0x1800051c0  movups  xmmword ptr [rax+30h], xmm1
0x1800051c4  movaps  xmm0, xmmword ptr [rbp+57h+var_90.pUnk]
0x1800051c8  movups  xmmword ptr [rax+40h], xmm0
0x1800051cc  movsd   xmm1, [rbp+57h+var_90.pbFormat]
0x1800051d1  movsd   qword ptr [rax+50h], xmm1
0x1800051d6  mov     [rbp+57h+var_90.pbFormat], 0
0x1800051de  mov     [rbp+57h+var_90.cbFormat], 0
0x1800051e5  mov     [rbp+57h+var_90.pUnk], 0
0x1800051ed  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800051f2  add     ebx, 0FFFFFFFFh
0x1800051f5  jnz     loc_180005144
0x1800051fb  jmp     short loc_180005216
0x1800051fd  cmp     ebx, 1
0x180005200  jbe     loc_180005139
0x180005206  mov     eax, 80070057h
0x18000520b  jmp     short loc_18000522C
0x18000520d  lea     rcx, [rbp+57h+var_90]; struct _AMMediaType *
0x180005211  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180005216  test    rdi, rdi
0x180005219  jz      short loc_18000521E
0x18000521b  mov     [rdi], r14d
0x18000521e  xor     eax, eax
0x180005220  test    ebx, ebx
0x180005222  setnz   al
0x180005225  jmp     short loc_18000522C
0x180005227  mov     eax, 80040203h
0x18000522c  mov     rcx, [rbp+57h+var_30]
0x180005230  xor     rcx, rsp; StackCookie
0x180005233  call    __security_check_cookie
0x180005238  mov     rbx, [rsp+0B0h+arg_8]
0x180005240  add     rsp, 90h
0x180005247  pop     r15
0x180005249  pop     r14
0x18000524b  pop     rdi
0x18000524c  pop     rsi
0x18000524d  pop     rbp
0x18000524e  retn
```
