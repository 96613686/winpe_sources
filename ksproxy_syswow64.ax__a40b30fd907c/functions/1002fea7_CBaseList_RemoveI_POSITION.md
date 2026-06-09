# CBaseList::RemoveI(__POSITION *)

- ea: `0x1002fea7`
- end: `0x1002ff09`
- name: `?RemoveI@CBaseList@@IAEPAXPAU__POSITION@@@Z`
- size: `98`
- prototype: `int __thiscall(CBaseList *this, CBaseList::CNode *Block)`
- caller_count: `11`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x10009f60`
- `0x100173a0`
- `0x10018300`
- `0x1001cd50`
- `0x1001d6ae`
- `0x1001d8a0`
- `0x1001d9fe`
- `0x10021391`
- `0x100213de`
- `0x1002179f`
- `0x1002be36`

## callees

- `0x1002fea7`
- `0x1003af9d`

## pseudocode

```c
int __thiscall CBaseList::RemoveI(CBaseList *this, CBaseList::CNode *Block)
{
  CBaseList::CNode *m_pNext; // eax
  CBaseList::CNode *v5; // ecx
  CBaseList::CNode *m_pPrev; // eax
  int m_pObject; // edi

  if ( !Block )
    return 0;
  m_pNext = Block->m_pNext;
  if ( Block->m_pPrev )
    Block->m_pPrev->m_pNext = m_pNext;
  else
    this->m_pFirst = m_pNext;
  v5 = Block->m_pNext;
  m_pPrev = Block->m_pPrev;
  if ( v5 )
    v5->m_pPrev = m_pPrev;
  else
    this->m_pLast = m_pPrev;
  m_pObject = (int)Block->m_pObject;
  if ( this->m_Cache.m_iUsed >= this->m_Cache.m_iCacheSize )
  {
    operator delete(Block, 0xCu);
  }
  else
  {
    Block->m_pNext = this->m_Cache.m_pHead;
    ++this->m_Cache.m_iUsed;
    this->m_Cache.m_pHead = Block;
  }
  --this->m_Count;
  return m_pObject;
}

```

## disassembly

```asm
0x1002fea7  mov     edi, edi
0x1002fea9  push    ebp
0x1002feaa  mov     ebp, esp
0x1002feac  mov     edx, [ebp+Block]
0x1002feaf  push    esi
0x1002feb0  mov     esi, ecx
0x1002feb2  test    edx, edx
0x1002feb4  jnz     short loc_1002FEBA
0x1002feb6  xor     eax, eax
0x1002feb8  jmp     short loc_1002FF04
0x1002feba  mov     ecx, [edx]
0x1002febc  mov     eax, [edx+4]
0x1002febf  test    ecx, ecx
0x1002fec1  jnz     short loc_1002FEC7
0x1002fec3  mov     [esi], eax
0x1002fec5  jmp     short loc_1002FECA
0x1002fec7  mov     [ecx+4], eax
0x1002feca  mov     ecx, [edx+4]
0x1002fecd  mov     eax, [edx]
0x1002fecf  test    ecx, ecx
0x1002fed1  jnz     short loc_1002FED8
0x1002fed3  mov     [esi+4], eax
0x1002fed6  jmp     short loc_1002FEDA
0x1002fed8  mov     [ecx], eax
0x1002feda  mov     eax, [esi+10h]
0x1002fedd  push    edi
0x1002fede  mov     edi, [edx+8]
0x1002fee1  cmp     eax, [esi+0Ch]
0x1002fee4  jge     short loc_1002FEF4
0x1002fee6  mov     eax, [esi+14h]
0x1002fee9  mov     [edx+4], eax
0x1002feec  inc     dword ptr [esi+10h]
0x1002feef  mov     [esi+14h], edx
0x1002fef2  jmp     short loc_1002FEFE
0x1002fef4  push    0Ch; unsigned int
0x1002fef6  push    edx; Block
0x1002fef7  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1002fefc  pop     ecx
0x1002fefd  pop     ecx
0x1002fefe  dec     dword ptr [esi+8]
0x1002ff01  mov     eax, edi
0x1002ff03  pop     edi
0x1002ff04  pop     esi
0x1002ff05  pop     ebp
0x1002ff06  retn    4
```
