# FREB_REQUEST_CONTEXT::InitializeInstance(FREB_META_STORED_CONTEXT *,int)

- ea: `0x180004440`
- end: `0x1800045fb`
- name: `?InitializeInstance@FREB_REQUEST_CONTEXT@@QEAAJPEAVFREB_META_STORED_CONTEXT@@H@Z`
- size: `443`
- prototype: `__int64 __fastcall(FREB_REQUEST_CONTEXT *__hidden this, struct FREB_META_STORED_CONTEXT *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800023cc`
- `0x180003654`

## callees

- `0x180004440`
- `0x18000ac52`
- `0x18000ac90`
- `0x18000b010`

## import_xrefs

- `msvcrt!towupper` at `0x180004529`
- `msvcrt!towupper` at `0x180004565`
- `msvcrt!towupper` at `0x180004529`
- `msvcrt!towupper` at `0x180004565`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800045ce`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800045ce`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004491`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004491`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800044d2`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800044d2`

## pseudocode

```c
__int64 __fastcall FREB_REQUEST_CONTEXT::InitializeInstance(
        FREB_REQUEST_CONTEXT *this,
        struct FREB_META_STORED_CONTEXT *a2,
        int a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned int v8; // r12d
  __int64 v9; // rsi
  unsigned int v10; // ebp
  wint_t *v11; // rcx
  wint_t *v12; // rdi
  __int64 v13; // r13
  _WORD *i; // rbx
  __int16 v15; // r14
  _WORD *v16; // r12
  wint_t *v17; // r14
  __int64 v18; // rax
  int v20; // [rsp+20h] [rbp-1A8h]
  wint_t *v21; // [rsp+28h] [rbp-1A0h]
  _BYTE v22[32]; // [rsp+30h] [rbp-198h] BYREF
  wint_t *v23; // [rsp+50h] [rbp-178h]
  unsigned __int16 v24[128]; // [rsp+70h] [rbp-158h] BYREF

  memset_0(v24, 0, sizeof(v24));
  STRU::STRU((STRU *)v22, v24, 0x80u);
  v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6));
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  *((_QWORD *)this + 7) = a2;
  *((_DWORD *)this + 16) = a3;
  v20 = STRU::Copy((STRU *)v22, *(const unsigned __int16 **)(v7 + 88), *(unsigned __int16 *)(v7 + 68) >> 1);
  v8 = v20;
  if ( v20 >= 0 )
  {
    v9 = *((_QWORD *)this + 7);
    if ( v9 )
    {
      v10 = 0;
      v11 = v23;
      v21 = v23;
      if ( *(_DWORD *)(v9 + 16) )
      {
        while ( 2 )
        {
          v12 = v11;
          v13 = 224LL * v10;
          for ( i = *(_WORD **)(*(_QWORD *)(v9 + 8) + v13 + 32); *i != 42; ++i )
          {
            v15 = *i;
            if ( towupper(*v12) != v15 )
              goto LABEL_19;
            if ( !v15 )
            {
LABEL_21:
              v8 = v20;
              v18 = v13 + *(_QWORD *)(v9 + 8);
              goto LABEL_24;
            }
            ++v12;
          }
LABEL_11:
          v16 = i;
          while ( 2 )
          {
            v17 = v12;
            while ( 1 )
            {
              if ( *i == 42 )
              {
                if ( !*++i )
                  goto LABEL_21;
                goto LABEL_11;
              }
              if ( towupper(*v12) != *i )
                break;
              if ( !*i )
                goto LABEL_21;
              ++v12;
              ++i;
            }
            v12 = v17 + 1;
            if ( v17[1] )
            {
              i = v16;
              continue;
            }
            break;
          }
LABEL_19:
          if ( ++v10 < *(_DWORD *)(v9 + 16) )
          {
            v11 = v21;
            continue;
          }
          break;
        }
        v8 = v20;
      }
      v18 = 0;
LABEL_24:
      *((_QWORD *)this + 10) = v18;
      if ( v18 )
        *((_DWORD *)this + 22) = *(_DWORD *)(v18 + 196);
    }
  }
  STRU::~STRU((STRU *)v22);
  return v8;
}

```

## disassembly

```asm
0x180004440  push    rbx
0x180004442  push    rbp
0x180004443  push    rsi
0x180004444  push    rdi
0x180004445  push    r12
0x180004447  push    r13
0x180004449  push    r14
0x18000444b  push    r15
0x18000444d  sub     rsp, 188h
0x180004454  mov     rax, cs:__security_cookie
0x18000445b  xor     rax, rsp
0x18000445e  mov     [rsp+1C8h+var_58], rax
0x180004466  mov     edi, r8d
0x180004469  mov     rbx, rdx
0x18000446c  mov     r15, rcx
0x18000446f  xor     edx, edx; Val
0x180004471  mov     r8d, 100h; Size
0x180004477  lea     rcx, [rsp+1C8h+var_158]; void *
0x18000447c  call    memset_0
0x180004481  mov     r8d, 80h
0x180004487  lea     rdx, [rsp+1C8h+var_158]
0x18000448c  lea     rcx, [rsp+1C8h+var_198]
0x180004491  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004497  mov     rcx, [r15+30h]
0x18000449b  mov     rax, [rcx]
0x18000449e  mov     rax, [rax+18h]
0x1800044a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a7  mov     rdx, rax
0x1800044aa  mov     rcx, [rax]
0x1800044ad  mov     rax, [rcx+8]
0x1800044b1  mov     rcx, rdx
0x1800044b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044b9  mov     [r15+38h], rbx
0x1800044bd  lea     rcx, [rsp+1C8h+var_198]
0x1800044c2  mov     [r15+40h], edi
0x1800044c6  movzx   r8d, word ptr [rax+44h]
0x1800044cb  mov     rdx, [rax+58h]
0x1800044cf  shr     r8d, 1
0x1800044d2  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800044d8  xor     edx, edx
0x1800044da  mov     [rsp+1C8h+var_1A8], eax
0x1800044de  mov     r12d, eax
0x1800044e1  test    eax, eax
0x1800044e3  js      loc_1800045C9
0x1800044e9  mov     rsi, [r15+38h]
0x1800044ed  test    rsi, rsi
0x1800044f0  jz      loc_1800045C9
0x1800044f6  mov     ebp, edx
0x1800044f8  mov     rcx, [rsp+1C8h+var_178]
0x1800044fd  mov     [rsp+1C8h+var_1A0], rcx
0x180004502  cmp     [rsi+10h], edx
0x180004505  jbe     loc_1800045B3
0x18000450b  mov     eax, ebp
0x18000450d  mov     rdi, rcx
0x180004510  imul    r13, rax, 0E0h
0x180004517  mov     rax, [rsi+8]
0x18000451b  mov     rbx, [rax+r13+20h]
0x180004520  jmp     short loc_180004545
0x180004522  movzx   ecx, word ptr [rdi]; C
0x180004525  movzx   r14d, word ptr [rbx]
0x180004529  call    cs:__imp_towupper
0x18000452f  xor     edx, edx
0x180004531  cmp     ax, r14w
0x180004535  jnz     short loc_18000458F
0x180004537  test    r14w, r14w
0x18000453b  jz      short loc_1800045A0
0x18000453d  add     rdi, 2
0x180004541  add     rbx, 2
0x180004545  cmp     word ptr [rbx], 2Ah ; '*'
0x180004549  jnz     short loc_180004522
0x18000454b  jmp     short loc_180004556
0x18000454d  add     rbx, 2
0x180004551  cmp     [rbx], dx
0x180004554  jz      short loc_1800045A0
0x180004556  mov     r12, rbx
0x180004559  mov     r14, rdi
0x18000455c  cmp     word ptr [rbx], 2Ah ; '*'
0x180004560  jz      short loc_18000454D
0x180004562  movzx   ecx, word ptr [rdi]; C
0x180004565  call    cs:__imp_towupper
0x18000456b  xor     edx, edx
0x18000456d  cmp     ax, [rbx]
0x180004570  jz      short loc_180004580
0x180004572  lea     rdi, [r14+2]
0x180004576  cmp     [rdi], dx
0x180004579  jz      short loc_18000458F
0x18000457b  mov     rbx, r12
0x18000457e  jmp     short loc_180004559
0x180004580  cmp     [rbx], dx
0x180004583  jz      short loc_1800045A0
0x180004585  add     rdi, 2
0x180004589  add     rbx, 2
0x18000458d  jmp     short loc_18000455C
0x18000458f  inc     ebp
0x180004591  cmp     ebp, [rsi+10h]
0x180004594  jnb     short loc_1800045AE
0x180004596  mov     rcx, [rsp+1C8h+var_1A0]
0x18000459b  jmp     loc_18000450B
0x1800045a0  mov     rax, [rsi+8]
0x1800045a4  mov     r12d, [rsp+1C8h+var_1A8]
0x1800045a9  add     rax, r13
0x1800045ac  jmp     short loc_1800045B6
0x1800045ae  mov     r12d, [rsp+1C8h+var_1A8]
0x1800045b3  mov     rax, rdx
0x1800045b6  mov     [r15+50h], rax
0x1800045ba  test    rax, rax
0x1800045bd  jz      short loc_1800045C9
0x1800045bf  mov     eax, [rax+0C4h]
0x1800045c5  mov     [r15+58h], eax
0x1800045c9  lea     rcx, [rsp+1C8h+var_198]
0x1800045ce  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800045d4  mov     eax, r12d
0x1800045d7  mov     rcx, [rsp+1C8h+var_58]
0x1800045df  xor     rcx, rsp; StackCookie
0x1800045e2  call    __security_check_cookie
0x1800045e7  add     rsp, 188h
0x1800045ee  pop     r15
0x1800045f0  pop     r14
0x1800045f2  pop     r13
0x1800045f4  pop     r12
0x1800045f6  pop     rdi
0x1800045f7  pop     rsi
0x1800045f8  pop     rbp
0x1800045f9  pop     rbx
0x1800045fa  retn
```
