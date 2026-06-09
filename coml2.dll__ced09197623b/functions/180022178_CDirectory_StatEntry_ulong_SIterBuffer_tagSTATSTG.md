# CDirectory::StatEntry(ulong,SIterBuffer *,tagSTATSTG *)

- ea: `0x180022178`
- end: `0x1800222f4`
- name: `?StatEntry@CDirectory@@QEAAJKPEAUSIterBuffer@@PEAUtagSTATSTG@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(CDirectory *__hidden this, unsigned int, struct SIterBuffer *, struct tagSTATSTG *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022030`
- `0x180060a48`

## callees

- `0x18000eff0`
- `0x180013160`
- `0x180022178`
- `0x1800222fc`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002222e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002222e`

## pseudocode

```c
__int64 __fastcall CDirectory::StatEntry(
        CDirectory *this,
        unsigned int a2,
        struct SIterBuffer *a3,
        struct tagSTATSTG *a4)
{
  int DirEntry; // esi
  unsigned __int8 *v9; // rbx
  SIZE_T v10; // rbp
  _WORD *v11; // rcx
  __int64 v12; // rax
  int v13; // ecx
  void *v14; // rax
  bool v15; // zf
  __int64 v16; // rax
  __int64 v17; // rax
  void *Src; // [rsp+20h] [rbp-58h] BYREF

  Src = 0;
  DirEntry = CDirectory::GetDirEntry(this, a2, 0, (struct CDirEntry **)&Src);
  if ( DirEntry >= 0 )
  {
    v9 = (unsigned __int8 *)Src;
    v10 = *((__int16 *)Src + 32);
    if ( v10 > 0x40 || !Src )
      goto LABEL_22;
    v11 = Src;
    v12 = 32;
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v12;
    }
    while ( v12 );
    if ( v12
      && v10 == ((2 * (32 - v12)) & -(__int64)(v12 != 0)) + 2
      && (v13 = *((unsigned __int8 *)Src + 66), (unsigned int)(v13 - 1) <= 1) )
    {
      if ( a3 )
      {
        CDfName::Set(a3, (const struct CDfName *)Src);
        *((_DWORD *)a3 + 17) = v9[66];
      }
      else
      {
        *((_DWORD *)a4 + 2) = v13;
        v14 = CoTaskMemAlloc(v10);
        *(_QWORD *)a4 = v14;
        if ( v14 )
        {
          memcpy_0(v14, v9, v10);
          v15 = *((_DWORD *)a4 + 2) == 1;
          *((_QWORD *)a4 + 4) = *(_QWORD *)(v9 + 100);
          v16 = *(_QWORD *)(v9 + 108);
          *((_QWORD *)a4 + 3) = v16;
          *((_QWORD *)a4 + 5) = v16;
          if ( v15 )
          {
            *((_QWORD *)a4 + 2) = 0;
            *(_OWORD *)((char *)a4 + 56) = *((_OWORD *)v9 + 5);
            *((_DWORD *)a4 + 18) = *((_DWORD *)v9 + 24);
          }
          else if ( *((_DWORD *)a4 + 2) == 2 )
          {
            if ( *((_WORD *)this + 36) > 4u )
              v17 = *((_QWORD *)v9 + 15);
            else
              v17 = *((unsigned int *)v9 + 30);
            *((_QWORD *)a4 + 2) = v17;
            *((_DWORD *)a4 + 18) = 0;
            *(GUID *)((char *)a4 + 56) = GUID_NULL;
          }
        }
        else
        {
          DirEntry = -2147287032;
        }
      }
    }
    else
    {
LABEL_22:
      DirEntry = -2147286775;
    }
    CPagedVector::ReleaseTable(this, a2 / *((unsigned __int16 *)this + 36));
  }
  return (unsigned int)DirEntry;
}

```

## disassembly

```asm
0x180022178  push    rbx
0x18002217a  push    rbp
0x18002217b  push    rsi
0x18002217c  push    rdi
0x18002217d  push    r12
0x18002217f  push    r13
0x180022181  push    r14
0x180022183  push    r15
0x180022185  sub     rsp, 38h
0x180022189  mov     rdi, r9
0x18002218c  mov     r14, r8
0x18002218f  xor     r13d, r13d
0x180022192  lea     r9, [rsp+78h+Src]; struct CDirEntry **
0x180022197  xor     r8d, r8d; unsigned int
0x18002219a  mov     [rsp+78h+Src], r13
0x18002219f  mov     r12d, edx
0x1800221a2  mov     r15, rcx
0x1800221a5  call    ?GetDirEntry@CDirectory@@QEAAJKKPEAPEAVCDirEntry@@@Z; CDirectory::GetDirEntry(ulong,ulong,CDirEntry * *)
0x1800221aa  mov     esi, eax
0x1800221ac  test    eax, eax
0x1800221ae  js      loc_1800222A3
0x1800221b4  mov     rbx, [rsp+78h+Src]
0x1800221b9  movsx   rbp, word ptr [rbx+40h]
0x1800221be  cmp     rbp, 40h ; '@'
0x1800221c2  ja      loc_1800222D8
0x1800221c8  test    rbx, rbx
0x1800221cb  jz      loc_1800222D8
0x1800221d1  lea     edx, [r13+20h]
0x1800221d5  mov     rcx, rbx
0x1800221d8  mov     eax, edx
0x1800221da  cmp     [rcx], r13w
0x1800221de  jz      short loc_1800221EA
0x1800221e0  add     rcx, 2
0x1800221e4  sub     rax, 1
0x1800221e8  jnz     short loc_1800221DA
0x1800221ea  test    rax, rax
0x1800221ed  jz      loc_1800222D8
0x1800221f3  sub     rdx, rax
0x1800221f6  add     rdx, rdx
0x1800221f9  neg     rax
0x1800221fc  sbb     rax, rax
0x1800221ff  and     rax, rdx
0x180022202  add     rax, 2
0x180022206  cmp     rbp, rax
0x180022209  jnz     loc_1800222D8
0x18002220f  movzx   ecx, byte ptr [rbx+42h]
0x180022213  lea     eax, [rcx-1]
0x180022216  cmp     eax, 1
0x180022219  ja      loc_1800222D8
0x18002221f  test    r14, r14
0x180022222  jnz     loc_1800222B6
0x180022228  mov     [rdi+8], ecx
0x18002222b  mov     rcx, rbp; cb
0x18002222e  call    cs:__imp_CoTaskMemAlloc
0x180022234  mov     [rdi], rax
0x180022237  test    rax, rax
0x18002223a  jz      loc_1800222CB
0x180022240  mov     r8, rbp; Size
0x180022243  mov     rdx, rbx; Src
0x180022246  mov     rcx, rax; void *
0x180022249  call    memcpy_0
0x18002224e  cmp     dword ptr [rdi+8], 1
0x180022252  mov     rax, [rbx+64h]
0x180022256  mov     [rdi+20h], rax
0x18002225a  mov     rax, [rbx+6Ch]
0x18002225e  mov     [rdi+18h], rax
0x180022262  mov     [rdi+28h], rax
0x180022266  jz      short loc_1800222DF
0x180022268  cmp     dword ptr [rdi+8], 2
0x18002226c  jnz     short loc_18002228D
0x18002226e  cmp     word ptr [r15+48h], 4
0x180022274  ja      short loc_1800222D2
0x180022276  mov     eax, [rbx+78h]
0x180022279  mov     [rdi+10h], rax
0x18002227d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180022284  mov     [rdi+48h], r13d
0x180022288  movdqu  xmmword ptr [rdi+38h], xmm0
0x18002228d  movzx   ecx, word ptr [r15+48h]
0x180022292  xor     edx, edx
0x180022294  mov     eax, r12d
0x180022297  div     ecx
0x180022299  mov     rcx, r15; this
0x18002229c  mov     edx, eax; unsigned int
0x18002229e  call    ?ReleaseTable@CPagedVector@@QEAAXK@Z; CPagedVector::ReleaseTable(ulong)
0x1800222a3  mov     eax, esi
0x1800222a5  add     rsp, 38h
0x1800222a9  pop     r15
0x1800222ab  pop     r14
0x1800222ad  pop     r13
0x1800222af  pop     r12
0x1800222b1  pop     rdi
0x1800222b2  pop     rsi
0x1800222b3  pop     rbp
0x1800222b4  pop     rbx
0x1800222b5  retn
0x1800222b6  mov     rdx, rbx; struct CDfName *
0x1800222b9  mov     rcx, r14; this
0x1800222bc  call    ?Set@CDfName@@QEAAXPEBV1@@Z; CDfName::Set(CDfName const *)
0x1800222c1  movzx   eax, byte ptr [rbx+42h]
0x1800222c5  mov     [r14+44h], eax
0x1800222c9  jmp     short loc_18002228D
0x1800222cb  mov     esi, 80030008h
0x1800222d0  jmp     short loc_18002228D
0x1800222d2  mov     rax, [rbx+78h]
0x1800222d6  jmp     short loc_180022279
0x1800222d8  mov     esi, 80030109h
0x1800222dd  jmp     short loc_18002228D
0x1800222df  mov     [rdi+10h], r13
0x1800222e3  movups  xmm0, xmmword ptr [rbx+50h]
0x1800222e7  movdqu  xmmword ptr [rdi+38h], xmm0
0x1800222ec  mov     eax, [rbx+60h]
0x1800222ef  mov     [rdi+48h], eax
0x1800222f2  jmp     short loc_18002228D
```
