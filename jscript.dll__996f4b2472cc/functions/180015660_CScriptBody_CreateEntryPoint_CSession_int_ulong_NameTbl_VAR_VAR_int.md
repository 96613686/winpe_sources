# CScriptBody::CreateEntryPoint(CSession *,int,ulong,NameTbl * *,VAR *,VAR *,int)

- ea: `0x180015660`
- end: `0x18001588b`
- name: `?CreateEntryPoint@CScriptBody@@QEAAJPEAVCSession@@HKPEAPEAVNameTbl@@PEAVVAR@@2H@Z`
- size: `555`
- prototype: `int(CScriptBody *__hidden this, struct CSession *, int, unsigned int, struct NameTbl **, struct VAR *, struct VAR *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180023440`

## callees

- `0x18000b0e0`
- `0x18000c4a0`
- `0x180015660`
- `0x180015894`
- `0x1800585d0`

## import_xrefs

- `msvcrt!malloc` at `0x180015825`
- `msvcrt!malloc` at `0x180015825`

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
0x180015660  push    rbx
0x180015662  push    rbp
0x180015663  push    rsi
0x180015664  push    rdi
0x180015665  push    r12
0x180015667  push    r13
0x180015669  push    r14
0x18001566b  push    r15
0x18001566d  sub     rsp, 48h
0x180015671  mov     r13d, r9d
0x180015674  mov     r15, rdx
0x180015677  mov     rbp, rcx
0x18001567a  test    r8d, r8d
0x18001567d  js      loc_180015881
0x180015683  mov     rax, [rcx+40h]
0x180015687  cmp     r8d, [rax+1Ch]
0x18001568b  jge     loc_180015881
0x180015691  mov     r12, [rcx+48h]
0x180015695  mov     edx, 3; int
0x18001569a  movsxd  rax, dword ptr [rax+18h]
0x18001569e  mov     rcx, r15; this
0x1800156a1  movsxd  r8, r8d
0x1800156a4  add     rax, r12
0x1800156a7  movsxd  rbx, dword ptr [rax+r8*4]
0x1800156ab  lea     r8, [rsp+88h+var_68]; struct VAR *
0x1800156b0  call    ?GetTypeProto@CSession@@QEAAJHPEAVVAR@@@Z; CSession::GetTypeProto(int,VAR *)
0x1800156b5  test    eax, eax
0x1800156b7  js      loc_1800157DB
0x1800156bd  mov     ecx, 0D8h; Size
0x1800156c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800156c7  mov     r14, rax
0x1800156ca  test    rax, rax
0x1800156cd  jz      loc_1800157ED
0x1800156d3  lea     rax, ??_7NameTbl@@6B@; const NameTbl::`vftable'
0x1800156da  lea     rsi, [r12+rbx]
0x1800156de  movsx   edi, word ptr [rsi+2Ch]
0x1800156e2  lea     rcx, [r14+40h]; this
0x1800156e6  mov     [r14], rax
0x1800156e9  mov     rdx, [r15+3D8h]; struct ThreadGlobals *
0x1800156f0  call    ??0IScavengerBase@@QEAA@PEAVThreadGlobals@@@Z; IScavengerBase::IScavengerBase(ThreadGlobals *)
0x1800156f5  lea     rax, ??_7ObjectRegistration@@6B@; const ObjectRegistration::`vftable'
0x1800156fc  mov     [r14+40h], rax
0x180015700  lock inc cs:?g_cLibRef@@3JA; long g_cLibRef
0x180015707  mov     qword ptr [r14+10h], 0
0x18001570f  mov     [r14+18h], r15
0x180015713  lock inc dword ptr [r15]
0x180015717  xor     r15d, r15d
0x18001571a  mov     dword ptr [r14+28h], 0FFFFFFFFh
0x180015722  lea     rax, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x180015729  mov     [r14+38h], r15
0x18001572d  mov     [r14+20h], rax
0x180015731  mov     rax, [rsp+88h+var_60]
0x180015736  mov     [r14+8], r15d
0x18001573a  mov     [r14+30h], rax
0x18001573e  lea     rax, ?cbstrFunction@@3UConstBstr@@A; ConstBstr cbstrFunction
0x180015745  mov     [r14+60h], rax
0x180015749  lea     rax, ??_7ScrFncObj@@6B@; const ScrFncObj::`vftable'
0x180015750  mov     [r14], rax
0x180015753  mov     [r14+68h], edi
0x180015757  mov     [r14+70h], r15w
0x18001575c  mov     [r14+88h], rbp
0x180015763  lock inc dword ptr [rbp+0]
0x180015767  and     dword ptr [r14+0C0h], 0FFFFFFFEh
0x18001576f  mov     ebx, r15d
0x180015772  mov     eax, [rsp+88h+var_4C]
0x180015776  mov     rdi, [rsp+88h+arg_28]
0x18001577e  mov     [r14+0A0h], rsi
0x180015785  mov     rsi, [rsp+88h+arg_20]
0x18001578d  mov     [r14+90h], rbp
0x180015794  mov     rbp, [rsp+88h+arg_30]
0x18001579c  mov     [r14+0ACh], eax
0x1800157a3  mov     rax, rdi
0x1800157a6  mov     [r14+98h], r12
0x1800157ad  mov     [r14+0A8h], r13d
0x1800157b4  mov     [r14+0B8h], r15
0x1800157bb  mov     [r14+0D0h], r15d
0x1800157c2  mov     [r14+0C8h], r15
0x1800157c9  mov     [rsi], r14
0x1800157cc  mov     [r14+0B0h], r15d
0x1800157d3  cmp     rdi, rbp
0x1800157d6  jnz     short loc_180015803
0x1800157d8  mov     eax, r15d
0x1800157db  add     rsp, 48h
0x1800157df  pop     r15
0x1800157e1  pop     r14
0x1800157e3  pop     r13
0x1800157e5  pop     r12
0x1800157e7  pop     rdi
0x1800157e8  pop     rsi
0x1800157e9  pop     rbp
0x1800157ea  pop     rbx
0x1800157eb  retn
0x1800157ed  mov     rax, [rsp+88h+arg_20]
0x1800157f5  mov     qword ptr [rax], 0
0x1800157fc  mov     eax, 8007000Eh
0x180015801  jmp     short loc_1800157DB
0x180015803  mov     rax, [rax+10h]
0x180015807  inc     ebx
0x180015809  cmp     rax, rbp
0x18001580c  jnz     short loc_180015803
0x18001580e  test    ebx, ebx
0x180015810  jle     short loc_1800157D8
0x180015812  movsxd  rax, ebx
0x180015815  cmp     rax, 5555555h
0x18001581b  ja      short loc_18001586C
0x18001581d  lea     rcx, [rax+rax*2]
0x180015821  shl     rcx, 3; Size
0x180015825  call    cs:__imp_malloc
0x18001582c  nop     dword ptr [rax+rax+00h]
0x180015831  mov     [r14+0C8h], rax
0x180015838  test    rax, rax
0x18001583b  jz      short loc_18001586C
0x18001583d  mov     [r14+0D0h], ebx
0x180015844  test    ebx, ebx
0x180015846  jle     short loc_1800157D8
0x180015848  movups  xmm0, xmmword ptr [rdi]
0x18001584b  dec     ebx
0x18001584d  movups  xmmword ptr [rax], xmm0
0x180015850  movsd   xmm1, qword ptr [rdi+10h]
0x180015855  movsd   qword ptr [rax+10h], xmm1
0x18001585a  add     rax, 18h
0x18001585e  mov     rdi, [rdi+10h]
0x180015862  cmp     rdi, rbp
0x180015865  jnz     short loc_180015844
0x180015867  jmp     loc_1800157D8
0x18001586c  mov     rcx, [rsi]; this
0x18001586f  test    rcx, rcx
0x180015872  jz      short loc_1800157FC
0x180015874  call    ?Release@NameTbl@@UEAAKXZ; NameTbl::Release(void)
0x180015879  mov     [rsi], r15
0x18001587c  jmp     loc_1800157FC
0x180015881  mov     eax, 80004005h
0x180015886  jmp     loc_1800157DB
```
