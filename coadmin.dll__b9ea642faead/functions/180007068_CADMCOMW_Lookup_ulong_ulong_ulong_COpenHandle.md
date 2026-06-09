# CADMCOMW::Lookup(ulong,ulong *,ulong *,COpenHandle * *)

- ea: `0x180007068`
- end: `0x180007163`
- name: `?Lookup@CADMCOMW@@QEAAJKPEAK0PEAPEAVCOpenHandle@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, unsigned int *, unsigned int *, struct COpenHandle **)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003160`
- `0x180004dd0`
- `0x180005048`
- `0x180005bd0`
- `0x180005f70`
- `0x1800063c0`
- `0x18000716c`
- `0x180007f40`
- `0x18000f30c`

## callees

- `0x180007068`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007140`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007140`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800070ef`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800070ef`

## pseudocode

```c
__int64 __fastcall CADMCOMW::Lookup(
        CADMCOMW *this,
        unsigned int a2,
        unsigned int *a3,
        unsigned int *a4,
        struct COpenHandle **a5)
{
  unsigned int v9; // ebx
  __int64 *v10; // rax
  CReaderWriterLock3 *v11; // r12
  int v12; // esi
  __int64 *i; // rcx
  volatile signed __int32 *v14; // rax

  if ( a5 )
    *a5 = 0;
  if ( a3 && a4 )
  {
    v9 = 0;
    *a3 = 0;
    if ( a2 )
    {
      v11 = (CADMCOMW *)((char *)this + 800);
      v12 = 0;
      CReaderWriterLock3::ReadLock((CADMCOMW *)((char *)this + 800));
      for ( i = (__int64 *)*((_QWORD *)this + a2 % 5 + 6); i; i = (__int64 *)*i )
      {
        if ( *((_DWORD *)i + 2) == a2 )
        {
          v12 = 1;
          *a3 = *((_DWORD *)i + 3);
          *a4 = *((_DWORD *)i + 4);
          if ( a5 )
          {
            v14 = (volatile signed __int32 *)i[3];
            *a5 = (struct COpenHandle *)v14;
            _InterlockedAdd(v14 + 3, 1u);
          }
          break;
        }
      }
      CReaderWriterLock3::ReadUnlock(v11);
      if ( !v12 )
        return (unsigned int)-2147024890;
    }
    else
    {
      *a3 = dword_18001600C;
      *a4 = dword_180016010;
      if ( a5 )
      {
        v10 = off_180016018;
        *a5 = (struct COpenHandle *)off_180016018;
        _InterlockedAdd((volatile signed __int32 *)v10 + 3, 1u);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x180007068  push    rbx
0x18000706a  push    rbp
0x18000706b  push    rsi
0x18000706c  push    rdi
0x18000706d  push    r12
0x18000706f  push    r13
0x180007071  push    r14
0x180007073  push    r15
0x180007075  sub     rsp, 28h
0x180007079  mov     rdi, [rsp+68h+arg_20]
0x180007081  mov     r15, r9
0x180007084  mov     r14, r8
0x180007087  mov     ebp, edx
0x180007089  mov     r13, rcx
0x18000708c  test    rdi, rdi
0x18000708f  jz      short loc_180007098
0x180007091  mov     qword ptr [rdi], 0
0x180007098  test    r14, r14
0x18000709b  jnz     short loc_1800070A7
0x18000709d  mov     ebx, 80070057h
0x1800070a2  jmp     loc_180007150
0x1800070a7  test    r15, r15
0x1800070aa  jz      short loc_18000709D
0x1800070ac  xor     ebx, ebx
0x1800070ae  mov     [r8], ebx
0x1800070b1  test    ebp, ebp
0x1800070b3  jnz     short loc_1800070E3
0x1800070b5  mov     eax, cs:dword_18001600C
0x1800070bb  mov     [r8], eax
0x1800070be  mov     eax, cs:dword_180016010
0x1800070c4  mov     [r9], eax
0x1800070c7  test    rdi, rdi
0x1800070ca  jz      loc_180007150
0x1800070d0  mov     rax, cs:off_180016018
0x1800070d7  lea     esi, [rbx+1]
0x1800070da  mov     [rdi], rax
0x1800070dd  lock add [rax+0Ch], esi
0x1800070e1  jmp     short loc_180007150
0x1800070e3  lea     r12, [rcx+320h]
0x1800070ea  xor     esi, esi
0x1800070ec  mov     rcx, r12
0x1800070ef  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800070f5  mov     ecx, ebp
0x1800070f7  mov     eax, 0CCCCCCCDh
0x1800070fc  mul     ebp
0x1800070fe  shr     edx, 2
0x180007101  lea     eax, [rdx+rdx*4]
0x180007104  sub     ecx, eax
0x180007106  mov     rcx, [r13+rcx*8+30h]
0x18000710b  jmp     short loc_180007115
0x18000710d  cmp     [rcx+8], ebp
0x180007110  jz      short loc_18000711C
0x180007112  mov     rcx, [rcx]
0x180007115  test    rcx, rcx
0x180007118  jnz     short loc_18000710D
0x18000711a  jmp     short loc_18000713D
0x18000711c  mov     eax, [rcx+0Ch]
0x18000711f  mov     esi, 1
0x180007124  mov     [r14], eax
0x180007127  mov     eax, [rcx+10h]
0x18000712a  mov     [r15], eax
0x18000712d  test    rdi, rdi
0x180007130  jz      short loc_18000713D
0x180007132  mov     rax, [rcx+18h]
0x180007136  mov     [rdi], rax
0x180007139  lock add [rax+0Ch], esi
0x18000713d  mov     rcx, r12
0x180007140  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180007146  test    esi, esi
0x180007148  mov     eax, 80070006h
0x18000714d  cmovz   ebx, eax
0x180007150  mov     eax, ebx
0x180007152  add     rsp, 28h
0x180007156  pop     r15
0x180007158  pop     r14
0x18000715a  pop     r13
0x18000715c  pop     r12
0x18000715e  pop     rdi
0x18000715f  pop     rsi
0x180007160  pop     rbp
0x180007161  pop     rbx
0x180007162  retn
```
