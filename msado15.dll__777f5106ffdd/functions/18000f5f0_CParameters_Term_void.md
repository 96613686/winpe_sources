# CParameters::Term(void)

- ea: `0x18000f5f0`
- end: `0x18000f6a6`
- name: `?Term@CParameters@@UEAAJXZ`
- size: `182`
- prototype: `__int64 __fastcall(CParameters *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000f5f0`
- `0x18000f760`
- `0x18007dd20`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000f617`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000f617`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000f638`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000f638`

## pseudocode

```c
__int64 __fastcall CParameters::Term(CParameters *this)
{
  CParamBuffer *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rsi
  __int64 v6; // rdi
  __int64 v7; // r8

  v2 = (CParamBuffer *)*((_QWORD *)this + 18);
  if ( v2 )
  {
    CParamBuffer::Release(v2);
    *((_QWORD *)this + 18) = 0;
  }
  *((_BYTE *)this + 136) = 1;
  CReaderWriterLock3AR::WriteLock((CParameters *)((char *)this + 72));
  v4 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v4 )
  {
    LODWORD(v6) = *(_DWORD *)(v4 + 16);
    while ( (_DWORD)v6 )
    {
      v7 = (unsigned int)v6;
      v6 = (unsigned int)(v6 - 1);
      if ( (unsigned int)v6 < *(_DWORD *)(v4 + 16) )
      {
        v3 = *(_QWORD *)(*(_QWORD *)(v4 + 8) + 8 * v6);
        if ( v3 )
        {
          if ( v3 != v7 )
            (*(void (__fastcall **)(CParameters *))(*(_QWORD *)this + 352LL))(this);
        }
      }
    }
    CCollectionList::`scalar deleting destructor'((CCollectionList *)v4, v3);
  }
  CReaderWriterLock3AR::WriteUnlock((CParameters *)((char *)this + 72));
  return 0;
}

```

## disassembly

```asm
0x18000f5f0  push    rbx
0x18000f5f2  push    rbp
0x18000f5f3  push    rsi
0x18000f5f4  push    rdi
0x18000f5f5  sub     rsp, 28h
0x18000f5f9  mov     rbx, rcx
0x18000f5fc  mov     rcx, [rcx+90h]; this
0x18000f603  test    rcx, rcx
0x18000f606  jnz     loc_18000F691
0x18000f60c  lea     rcx, [rbx+48h]
0x18000f610  mov     byte ptr [rbx+88h], 1
0x18000f617  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x18000f61e  nop     dword ptr [rax+rax+00h]
0x18000f623  mov     rsi, [rbx+40h]
0x18000f627  mov     qword ptr [rbx+40h], 0
0x18000f62f  test    rsi, rsi
0x18000f632  jnz     short loc_18000F650
0x18000f634  lea     rcx, [rbx+48h]
0x18000f638  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x18000f63f  nop     dword ptr [rax+rax+00h]
0x18000f644  xor     eax, eax
0x18000f646  add     rsp, 28h
0x18000f64a  pop     rdi
0x18000f64b  pop     rsi
0x18000f64c  pop     rbp
0x18000f64d  pop     rbx
0x18000f64e  retn
0x18000f650  mov     edi, [rsi+10h]
0x18000f653  test    edi, edi
0x18000f655  jnz     short loc_18000F661
0x18000f657  mov     rcx, rsi; this
0x18000f65a  call    ??_GCCollectionList@@QEAAPEAXI@Z; CCollectionList::`scalar deleting destructor'(uint)
0x18000f65f  jmp     short loc_18000F634
0x18000f661  mov     r8d, edi
0x18000f664  dec     edi
0x18000f666  cmp     edi, [rsi+10h]
0x18000f669  jnb     short loc_18000F653
0x18000f66b  mov     rax, [rsi+8]
0x18000f66f  mov     rdx, [rax+rdi*8]
0x18000f673  test    rdx, rdx
0x18000f676  jz      short loc_18000F653
0x18000f678  cmp     rdx, r8
0x18000f67b  jz      short loc_18000F653
0x18000f67d  mov     rax, [rbx]
0x18000f680  mov     rcx, rbx
0x18000f683  mov     rax, [rax+160h]
0x18000f68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f68f  jmp     short loc_18000F653
0x18000f691  call    ?Release@CParamBuffer@@QEAAKXZ; CParamBuffer::Release(void)
0x18000f696  mov     qword ptr [rbx+90h], 0
0x18000f6a1  jmp     loc_18000F60C
```
