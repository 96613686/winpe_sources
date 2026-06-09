# CScriptBody::CreateEntryPoint(CSession *,int,ulong,NameTbl * *,VAR *,VAR *,int)

- ea: `0x18001879c`
- end: `0x1800189bd`
- name: `?CreateEntryPoint@CScriptBody@@QEAAJPEAVCSession@@HKPEAPEAVNameTbl@@PEAVVAR@@2H@Z`
- size: `545`
- prototype: `int(CScriptBody *__hidden this, struct CSession *, int, unsigned int, struct NameTbl **, struct VAR *, struct VAR *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180026230`

## callees

- `0x18000ded0`
- `0x18000f230`
- `0x18001879c`
- `0x1800189c4`
- `0x1800576a0`

## import_xrefs

- `msvcrt!malloc` at `0x180018960`
- `msvcrt!malloc` at `0x180018960`

## pseudocode

```c
__int64 __fastcall CScriptBody::CreateEntryPoint(
        CScriptBody *this,
        struct ThreadGlobals **a2,
        int a3,
        int a4,
        struct NameTbl **a5,
        struct VAR *a6,
        struct VAR *a7)
{
  __int64 v10; // rax
  __int64 v11; // r12
  __int64 v12; // rbx
  __int64 result; // rax
  _QWORD *v14; // r14
  __int64 v15; // rsi
  int v16; // edi
  __int64 v17; // rax
  int v18; // ebx
  struct VAR *v19; // rdi
  struct VAR *v20; // rax
  _QWORD *v21; // rax
  _BYTE v22[8]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v23; // [rsp+28h] [rbp-60h]
  int v24; // [rsp+3Ch] [rbp-4Ch]

  if ( a3 < 0 )
    return 2147500037LL;
  v10 = *((_QWORD *)this + 8);
  if ( a3 >= *(_DWORD *)(v10 + 28) )
    return 2147500037LL;
  v11 = *((_QWORD *)this + 9);
  v12 = *(int *)(v11 + *(int *)(v10 + 24) + 4LL * a3);
  result = CSession::GetTypeProto((CSession *)a2, 3u, (struct VAR *)v22);
  if ( (int)result >= 0 )
  {
    v14 = operator new(0xD8u);
    if ( v14 )
    {
      v15 = v11 + v12;
      v16 = *(__int16 *)(v11 + v12 + 44);
      *v14 = &NameTbl::`vftable';
      IScavengerBase::IScavengerBase((IScavengerBase *)(v14 + 8), a2[123]);
      v14[8] = &ObjectRegistration::`vftable';
      _InterlockedIncrement(&g_cLibRef);
      v14[2] = 0;
      v14[3] = a2;
      _InterlockedIncrement((volatile signed __int32 *)a2);
      *((_DWORD *)v14 + 10) = -1;
      v14[7] = 0;
      v14[4] = NameTbl::s_varNameTblConstructed;
      v17 = v23;
      *((_DWORD *)v14 + 2) = 0;
      v14[6] = v17;
      v14[12] = &cbstrFunction;
      *v14 = &ScrFncObj::`vftable';
      *((_DWORD *)v14 + 26) = v16;
      *((_WORD *)v14 + 56) = 0;
      v14[17] = this;
      _InterlockedIncrement((volatile signed __int32 *)this);
      *((_DWORD *)v14 + 48) &= ~1u;
      v18 = 0;
      LODWORD(v17) = v24;
      v19 = a6;
      v14[20] = v15;
      v14[18] = this;
      *((_DWORD *)v14 + 43) = v17;
      v20 = a6;
      v14[19] = v11;
      *((_DWORD *)v14 + 42) = a4;
      v14[23] = 0;
      *((_DWORD *)v14 + 52) = 0;
      v14[25] = 0;
      *a5 = (struct NameTbl *)v14;
      *((_DWORD *)v14 + 44) = 0;
      if ( a6 == a7 )
        return 0;
      do
      {
        v20 = (struct VAR *)*((_QWORD *)v20 + 2);
        ++v18;
      }
      while ( v20 != a7 );
      if ( v18 <= 0 )
        return 0;
      if ( (unsigned __int64)v18 <= 0x5555555 )
      {
        v21 = malloc(24LL * v18);
        v14[25] = v21;
        if ( v21 )
        {
          *((_DWORD *)v14 + 52) = v18;
          do
          {
            if ( v18 <= 0 )
              break;
            --v18;
            *(_OWORD *)v21 = *(_OWORD *)v19;
            v21[2] = *((_QWORD *)v19 + 2);
            v21 += 3;
            v19 = (struct VAR *)*((_QWORD *)v19 + 2);
          }
          while ( v19 != a7 );
          return 0;
        }
      }
      if ( *a5 )
      {
        NameTbl::Release(*a5);
        *a5 = 0;
      }
    }
    else
    {
      *a5 = 0;
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001879c  push    rbx
0x18001879e  push    rbp
0x18001879f  push    rsi
0x1800187a0  push    rdi
0x1800187a1  push    r12
0x1800187a3  push    r13
0x1800187a5  push    r14
0x1800187a7  push    r15
0x1800187a9  sub     rsp, 48h
0x1800187ad  mov     r13d, r9d
0x1800187b0  mov     r15, rdx
0x1800187b3  mov     rbp, rcx
0x1800187b6  test    r8d, r8d
0x1800187b9  js      loc_1800189B3
0x1800187bf  mov     rax, [rcx+40h]
0x1800187c3  cmp     r8d, [rax+1Ch]
0x1800187c7  jge     loc_1800189B3
0x1800187cd  mov     r12, [rcx+48h]
0x1800187d1  mov     edx, 3; int
0x1800187d6  movsxd  rax, dword ptr [rax+18h]
0x1800187da  mov     rcx, r15; this
0x1800187dd  movsxd  r8, r8d
0x1800187e0  add     rax, r12
0x1800187e3  movsxd  rbx, dword ptr [rax+r8*4]
0x1800187e7  lea     r8, [rsp+88h+var_68]; struct VAR *
0x1800187ec  call    ?GetTypeProto@CSession@@QEAAJHPEAVVAR@@@Z; CSession::GetTypeProto(int,VAR *)
0x1800187f1  test    eax, eax
0x1800187f3  js      loc_180018917
0x1800187f9  mov     ecx, 0D8h; Size
0x1800187fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018803  mov     r14, rax
0x180018806  test    rax, rax
0x180018809  jz      loc_180018928
0x18001880f  lea     rax, ??_7NameTbl@@6B@; const NameTbl::`vftable'
0x180018816  lea     rsi, [r12+rbx]
0x18001881a  movsx   edi, word ptr [rsi+2Ch]
0x18001881e  lea     rcx, [r14+40h]; this
0x180018822  mov     [r14], rax
0x180018825  mov     rdx, [r15+3D8h]; struct ThreadGlobals *
0x18001882c  call    ??0IScavengerBase@@QEAA@PEAVThreadGlobals@@@Z; IScavengerBase::IScavengerBase(ThreadGlobals *)
0x180018831  lea     rax, ??_7ObjectRegistration@@6B@; const ObjectRegistration::`vftable'
0x180018838  mov     [r14+40h], rax
0x18001883c  lock inc cs:?g_cLibRef@@3JA; long g_cLibRef
0x180018843  mov     qword ptr [r14+10h], 0
0x18001884b  mov     [r14+18h], r15
0x18001884f  lock inc dword ptr [r15]
0x180018853  xor     r15d, r15d
0x180018856  mov     dword ptr [r14+28h], 0FFFFFFFFh
0x18001885e  lea     rax, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x180018865  mov     [r14+38h], r15
0x180018869  mov     [r14+20h], rax
0x18001886d  mov     rax, [rsp+88h+var_60]
0x180018872  mov     [r14+8], r15d
0x180018876  mov     [r14+30h], rax
0x18001887a  lea     rax, ?cbstrFunction@@3UConstBstr@@A; ConstBstr cbstrFunction
0x180018881  mov     [r14+60h], rax
0x180018885  lea     rax, ??_7ScrFncObj@@6B@; const ScrFncObj::`vftable'
0x18001888c  mov     [r14], rax
0x18001888f  mov     [r14+68h], edi
0x180018893  mov     [r14+70h], r15w
0x180018898  mov     [r14+88h], rbp
0x18001889f  lock inc dword ptr [rbp+0]
0x1800188a3  and     dword ptr [r14+0C0h], 0FFFFFFFEh
0x1800188ab  mov     ebx, r15d
0x1800188ae  mov     eax, [rsp+88h+var_4C]
0x1800188b2  mov     rdi, [rsp+88h+arg_28]
0x1800188ba  mov     [r14+0A0h], rsi
0x1800188c1  mov     rsi, [rsp+88h+arg_20]
0x1800188c9  mov     [r14+90h], rbp
0x1800188d0  mov     rbp, [rsp+88h+arg_30]
0x1800188d8  mov     [r14+0ACh], eax
0x1800188df  mov     rax, rdi
0x1800188e2  mov     [r14+98h], r12
0x1800188e9  mov     [r14+0A8h], r13d
0x1800188f0  mov     [r14+0B8h], r15
0x1800188f7  mov     [r14+0D0h], r15d
0x1800188fe  mov     [r14+0C8h], r15
0x180018905  mov     [rsi], r14
0x180018908  mov     [r14+0B0h], r15d
0x18001890f  cmp     rdi, rbp
0x180018912  jnz     short loc_18001893E
0x180018914  mov     eax, r15d
0x180018917  add     rsp, 48h
0x18001891b  pop     r15
0x18001891d  pop     r14
0x18001891f  pop     r13
0x180018921  pop     r12
0x180018923  pop     rdi
0x180018924  pop     rsi
0x180018925  pop     rbp
0x180018926  pop     rbx
0x180018927  retn
0x180018928  mov     rax, [rsp+88h+arg_20]
0x180018930  mov     qword ptr [rax], 0
0x180018937  mov     eax, 8007000Eh
0x18001893c  jmp     short loc_180018917
0x18001893e  mov     rax, [rax+10h]
0x180018942  inc     ebx
0x180018944  cmp     rax, rbp
0x180018947  jnz     short loc_18001893E
0x180018949  test    ebx, ebx
0x18001894b  jle     short loc_180018914
0x18001894d  movsxd  rax, ebx
0x180018950  cmp     rax, 5555555h
0x180018956  ja      short loc_1800189A1
0x180018958  lea     rcx, [rax+rax*2]
0x18001895c  shl     rcx, 3; Size
0x180018960  call    cs:__imp_malloc
0x180018966  mov     [r14+0C8h], rax
0x18001896d  test    rax, rax
0x180018970  jz      short loc_1800189A1
0x180018972  mov     [r14+0D0h], ebx
0x180018979  test    ebx, ebx
0x18001897b  jle     short loc_180018914
0x18001897d  movups  xmm0, xmmword ptr [rdi]
0x180018980  dec     ebx
0x180018982  movups  xmmword ptr [rax], xmm0
0x180018985  movsd   xmm1, qword ptr [rdi+10h]
0x18001898a  movsd   qword ptr [rax+10h], xmm1
0x18001898f  add     rax, 18h
0x180018993  mov     rdi, [rdi+10h]
0x180018997  cmp     rdi, rbp
0x18001899a  jnz     short loc_180018979
0x18001899c  jmp     loc_180018914
0x1800189a1  mov     rcx, [rsi]; this
0x1800189a4  test    rcx, rcx
0x1800189a7  jz      short loc_180018937
0x1800189a9  call    ?Release@NameTbl@@UEAAKXZ; NameTbl::Release(void)
0x1800189ae  mov     [rsi], r15
0x1800189b1  jmp     short loc_180018937
0x1800189b3  mov     eax, 80004005h
0x1800189b8  jmp     loc_180018917
```
