# _CopyCollection_CRecord_

- ea: `0x18000174c`
- end: `0x18000186a`
- name: `_CopyCollection_CRecord_`
- size: `286`
- prototype: `__int64 __fastcall(CStdCollection *this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001c98`

## callees

- `0x18000174c`
- `0x180002840`
- `0x180057c10`
- `0x18005b724`
- `0x1800cdaea`

## import_xrefs

- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001782`
- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001782`
- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001846`
- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180001846`
- `MSDART!MpHeapAlloc` at `0x1800017cf`
- `MSDART!MpHeapAlloc` at `0x1800017cf`

## pseudocode

```c
__int64 __fastcall CopyCollection_CRecord_(CStdCollection *this, _QWORD *a2, unsigned int *a3)
{
  CReaderWriterLock3AR *v3; // r15
  unsigned int Element; // ebx
  unsigned int Count; // eax
  unsigned int v9; // edi
  _QWORD *v10; // rax
  _QWORD *v11; // rsi
  __int64 v12; // rbp
  CStdCollection *v13; // r15
  CStdCollection *v14; // rax
  CStdCollection *v16; // [rsp+60h] [rbp+8h] BYREF
  size_t Size; // [rsp+68h] [rbp+10h] BYREF
  CReaderWriterLock3AR *v18; // [rsp+70h] [rbp+18h]

  v16 = this;
  v3 = (CStdCollection *)((char *)this + 72);
  Element = 0;
  *a2 = 0;
  *a3 = 0;
  v18 = (CStdCollection *)((char *)this + 72);
  CReaderWriterLock3AR::ReadLock((CStdCollection *)((char *)this + 72));
  Count = CStdCollection::GetCount(this);
  v9 = Count;
  if ( Count )
  {
    Size = 0;
    Element = ULongLongMult(Count, 8u, &Size);
    if ( !Element )
    {
      v10 = (_QWORD *)MpHeapAlloc(g_hHeapHandle, 10485760, Size);
      v11 = v10;
      if ( v10 )
      {
        memset_0(v10, 0, Size);
        v12 = 0;
        if ( v9 )
        {
          v13 = v16;
          do
          {
            v16 = 0;
            Element = CStdCollection::GetElement(v13, (unsigned int)v12, &v16);
            v14 = v16;
            if ( v16 )
              v14 = (CStdCollection *)((char *)v16 - 32);
            v11[v12] = v14;
            v12 = (unsigned int)(v12 + 1);
          }
          while ( (unsigned int)v12 < v9 );
          v3 = v18;
        }
        *a2 = v11;
        *a3 = v9;
      }
      else
      {
        Element = -2147024882;
      }
    }
  }
  CReaderWriterLock3AR::ReadUnlock(v3);
  return Element;
}

```

## disassembly

```asm
0x18000174c  mov     [rsp+arg_18], rbx
0x180001751  mov     [rsp+arg_0], rcx
0x180001756  push    rbp
0x180001757  push    rsi
0x180001758  push    rdi
0x180001759  push    r12
0x18000175b  push    r13
0x18000175d  push    r14
0x18000175f  push    r15
0x180001761  sub     rsp, 20h
0x180001765  lea     r15, [rcx+48h]
0x180001769  xor     ebx, ebx
0x18000176b  mov     rdi, rcx
0x18000176e  mov     [rdx], rbx
0x180001771  mov     rcx, r15
0x180001774  mov     [r8], ebx
0x180001777  mov     r12, r8
0x18000177a  mov     [rsp+58h+arg_10], r15
0x18000177f  mov     r13, rdx
0x180001782  call    cs:__imp_?ReadLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadLock(void)
0x180001789  nop     dword ptr [rax+rax+00h]
0x18000178e  mov     rcx, rdi; this
0x180001791  call    ?GetCount@CStdCollection@@UEAAKXZ; CStdCollection::GetCount(void)
0x180001796  mov     edi, eax
0x180001798  test    eax, eax
0x18000179a  jz      loc_180001843
0x1800017a0  mov     ecx, edi; unsigned __int64
0x1800017a2  mov     [rsp+58h+Size], rbx
0x1800017a7  lea     r8, [rsp+58h+Size]; unsigned __int64 *
0x1800017ac  lea     edx, [rbx+8]; unsigned __int64
0x1800017af  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800017b4  mov     ebx, eax
0x1800017b6  test    eax, eax
0x1800017b8  jnz     loc_180001843
0x1800017be  mov     r8, [rsp+58h+Size]
0x1800017c3  mov     edx, 0A00000h
0x1800017c8  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800017cf  call    cs:__imp_MpHeapAlloc
0x1800017d6  nop     dword ptr [rax+rax+00h]
0x1800017db  mov     rsi, rax
0x1800017de  test    rax, rax
0x1800017e1  jnz     short loc_1800017EA
0x1800017e3  mov     ebx, 8007000Eh
0x1800017e8  jmp     short loc_180001843
0x1800017ea  mov     r8, [rsp+58h+Size]; Size
0x1800017ef  xor     edx, edx; Val
0x1800017f1  mov     rcx, rsi; void *
0x1800017f4  call    memset_0
0x1800017f9  xor     ebp, ebp
0x1800017fb  test    edi, edi
0x1800017fd  jz      short loc_18000183B
0x1800017ff  mov     r15, [rsp+58h+arg_0]
0x180001804  lea     r8, [rsp+58h+arg_0]; struct CStdComObjectRoot **
0x180001809  mov     edx, ebp; unsigned __int64
0x18000180b  mov     rcx, r15; this
0x18000180e  mov     [rsp+58h+arg_0], 0
0x180001817  call    ?GetElement@CStdCollection@@QEAAJ_KPEAPEAVCStdComObjectRoot@@@Z; CStdCollection::GetElement(unsigned __int64,CStdComObjectRoot * *)
0x18000181c  mov     ebx, eax
0x18000181e  mov     rax, [rsp+58h+arg_0]
0x180001823  test    rax, rax
0x180001826  jz      short loc_18000182C
0x180001828  add     rax, 0FFFFFFFFFFFFFFE0h
0x18000182c  mov     [rsi+rbp*8], rax
0x180001830  inc     ebp
0x180001832  cmp     ebp, edi
0x180001834  jb      short loc_180001804
0x180001836  mov     r15, [rsp+58h+arg_10]
0x18000183b  mov     [r13+0], rsi
0x18000183f  mov     [r12], edi
0x180001843  mov     rcx, r15
0x180001846  call    cs:__imp_?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadUnlock(void)
0x18000184d  nop     dword ptr [rax+rax+00h]
0x180001852  mov     eax, ebx
0x180001854  mov     rbx, [rsp+58h+arg_18]
0x180001859  add     rsp, 20h
0x18000185d  pop     r15
0x18000185f  pop     r14
0x180001861  pop     r13
0x180001863  pop     r12
0x180001865  pop     rdi
0x180001866  pop     rsi
0x180001867  pop     rbp
0x180001868  retn
```
