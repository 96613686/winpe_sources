# ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)

- ea: `0x1800095a4`
- end: `0x1800096c0`
- name: `?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z`
- size: `284`
- prototype: `bool __fastcall(ATL::CDacl *this, const struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18000c478`

## callees

- `0x1800017f4`
- `0x180005c18`
- `0x180008888`
- `0x1800095a4`
- `0x18000bd70`
- `0x18000cad0`
- `0x18000d60c`
- `0x18002f010`

## import_xrefs

- `msvcrt!free` at `0x180009696`
- `msvcrt!free` at `0x180009696`

## pseudocode

```c
bool __fastcall ATL::CDacl::AddAllowedAce(ATL::CDacl *this, const struct ATL::CSid *a2)
{
  ATL::CDacl *v3; // rsi
  bool result; // al
  _DWORD *v5; // rbx
  unsigned __int64 v6; // r15
  _QWORD v7[7]; // [rsp+20h] [rbp-38h] BYREF

  v3 = this;
  result = ATL::CSid::IsValid(a2);
  if ( result )
  {
    if ( *((_BYTE *)v3 + 16) )
    {
      (*(void (__fastcall **)(ATL::CDacl *))(*(_QWORD *)v3 + 16LL))(v3);
      *((_BYTE *)v3 + 16) = 0;
    }
    try
    {
      v7[0] = 0;
      v5 = operator new(0x98u);
      v7[1] = v5;
      if ( v5 )
      {
        *(_QWORD *)v5 = &ATL::CAcl::CAce::`vftable';
        ATL::CSid::CSid((ATL::CSid *)(v5 + 2), a2);
        v5[32] = 0x10000000;
        *((_BYTE *)v5 + 132) = 0;
        *((_QWORD *)v5 + 17) = 0;
        *(_QWORD *)v5 = &ATL::CDacl::CAccessAce::`vftable';
        *((_BYTE *)v5 + 144) = 1;
      }
      v7[0] = v5;
    }
    catch ( ... )
    {
      v3 = this;
      v5 = (_DWORD *)v7[0];
    }
    if ( !v5
      || (v6 = *((_QWORD *)v3 + 4), v6 >= *((_QWORD *)v3 + 5))
      && !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
                             (char *)v3 + 24,
                             v6 + 1) )
    {
      ATL::AtlThrowImpl(-2147024882);
    }
    v7[0] = 0;
    *(_QWORD *)(*((_QWORD *)v3 + 3) + 8 * v6) = v5;
    ++*((_QWORD *)v3 + 4);
    free(*((void **)v3 + 1));
    *((_QWORD *)v3 + 1) = 0;
    ATL::CAutoPtr<ATL::CDacl::CAccessAce>::Free(v7);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800095a4  mov     [rsp+arg_0], rcx
0x1800095a9  push    rbx
0x1800095aa  push    rsi
0x1800095ab  push    r14
0x1800095ad  push    r15
0x1800095af  sub     rsp, 38h
0x1800095b3  mov     r14, rdx
0x1800095b6  mov     rsi, rcx
0x1800095b9  mov     rcx, rdx; this
0x1800095bc  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x1800095c1  test    al, al
0x1800095c3  jnz     short loc_1800095D0
0x1800095c5  add     rsp, 38h
0x1800095c9  pop     r15
0x1800095cb  pop     r14
0x1800095cd  pop     rsi
0x1800095ce  pop     rbx
0x1800095cf  retn
0x1800095d0  cmp     byte ptr [rsi+10h], 0
0x1800095d4  jz      short loc_1800095E9
0x1800095d6  mov     rax, [rsi]
0x1800095d9  mov     rcx, rsi
0x1800095dc  mov     rax, [rax+10h]
0x1800095e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e5  mov     byte ptr [rsi+10h], 0
0x1800095e9  mov     [rsp+58h+var_38], 0
0x1800095f2  mov     ecx, 98h; Size
0x1800095f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800095fc  mov     rbx, rax
0x1800095ff  mov     [rsp+58h+var_30], rax
0x180009604  test    rbx, rbx
0x180009607  jz      short loc_18000964C
0x180009609  lea     rax, ??_7CAce@CAcl@ATL@@6B@; const ATL::CAcl::CAce::`vftable'
0x180009610  mov     [rbx], rax
0x180009613  lea     rcx, [rbx+8]; this
0x180009617  mov     rdx, r14; struct ATL::CSid *
0x18000961a  call    ??0CSid@ATL@@QEAA@AEBV01@@Z; ATL::CSid::CSid(ATL::CSid const &)
0x18000961f  mov     dword ptr [rbx+80h], 10000000h
0x180009629  mov     byte ptr [rbx+84h], 0
0x180009630  mov     qword ptr [rbx+88h], 0
0x18000963b  lea     rax, ??_7CAccessAce@CDacl@ATL@@6B@; const ATL::CDacl::CAccessAce::`vftable'
0x180009642  mov     [rbx], rax
0x180009645  mov     byte ptr [rbx+90h], 1
0x18000964c  mov     [rsp+58h+var_38], rbx
0x180009651  jmp     short loc_18000965D
0x180009653  mov     rsi, [rsp+58h+arg_0]
0x180009658  mov     rbx, [rsp+58h+var_38]
0x18000965d  test    rbx, rbx
0x180009660  jz      short loc_1800096B5
0x180009662  mov     r15, [rsi+20h]
0x180009666  cmp     r15, [rsi+28h]
0x18000966a  jb      short loc_18000967D
0x18000966c  lea     rdx, [r15+1]
0x180009670  lea     rcx, [rsi+18h]
0x180009674  call    ?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)
0x180009679  test    al, al
0x18000967b  jz      short loc_1800096B5
0x18000967d  mov     [rsp+58h+var_38], 0
0x180009686  mov     rcx, [rsi+18h]
0x18000968a  mov     [rcx+r15*8], rbx
0x18000968e  inc     qword ptr [rsi+20h]
0x180009692  mov     rcx, [rsi+8]; Block
0x180009696  call    cs:__imp_free
0x18000969c  mov     qword ptr [rsi+8], 0
0x1800096a4  lea     rcx, [rsp+58h+var_38]
0x1800096a9  call    ?Free@?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@QEAAXXZ; ATL::CAutoPtr<ATL::CDacl::CAccessAce>::Free(void)
0x1800096ae  mov     al, 1
0x1800096b0  jmp     loc_1800095C5
0x1800096b5  mov     ecx, 8007000Eh; int
0x1800096ba  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
