# CHierarchyCache::InvalidateClass(ushort const *)

- ea: `0x18003e1f0`
- end: `0x18003e30f`
- name: `?InvalidateClass@CHierarchyCache@@QEAAJPEBG@Z`
- size: `287`
- prototype: `__int64 __fastcall(CHierarchyCache *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800253d4`
- `0x180031e48`

## callees

- `0x1800173d0`
- `0x180022a00`
- `0x18003e1f0`
- `0x18003e318`

## import_xrefs

- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18003e294`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18003e294`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18003e2a3`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18003e2b7`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18003e2a3`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18003e2b7`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003e20b`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003e20b`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003e2fa`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003e2fa`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18003e2c2`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18003e2c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHierarchyCache::InvalidateClass(struct _RTL_CRITICAL_SECTION **this, const unsigned __int16 *a2)
{
  volatile signed __int32 *Class; // rax
  CClassRecord *v5; // rbx
  unsigned int v6; // edi
  struct _RTL_CRITICAL_SECTION *v7; // rbp
  __int64 v8; // rax
  int v9; // esi
  CFlexArray *v10; // rbp
  __int64 i; // rcx
  char v13; // [rsp+40h] [rbp+8h] BYREF
  volatile signed __int32 *v14; // [rsp+50h] [rbp+18h]

  CInCritSec::CInCritSec((CInCritSec *)&v13, this[2]);
  Class = (volatile signed __int32 *)CHierarchyCache::FindClass(this, a2);
  v5 = (CClassRecord *)Class;
  v6 = 1;
  if ( Class )
  {
    _InterlockedAdd(Class + 2, 1u);
    v14 = Class;
    v7 = this[5];
    this[5] = (struct _RTL_CRITICAL_SECTION *)((char *)&v7->DebugInfo + 1);
    CHierarchyCache::InvalidateClassInternal((CHierarchyCache *)this, (struct CClassRecord *)Class);
    v8 = *((_QWORD *)v5 + 24);
    if ( v8 )
    {
      *(_BYTE *)(v8 + 305) = 0;
      *(_BYTE *)(*((_QWORD *)v5 + 24) + 304LL) = 0;
      *(_QWORD *)(*((_QWORD *)v5 + 24) + 312LL) = v7;
      v9 = 0;
      v10 = (CFlexArray *)(*((_QWORD *)v5 + 24) + 208LL);
      while ( v9 < CFlexArray::Size(v10) )
      {
        if ( CFlexArray::GetAt(v10, v9) == v5 )
        {
          CFlexArray::GetAt(v10, v9);
          CFlexArray::RemoveAt(v10, v9);
          break;
        }
        ++v9;
      }
      for ( i = *(_QWORD *)(*((_QWORD *)v5 + 24) + 192LL); i; i = *(_QWORD *)(i + 192) )
        *(_BYTE *)(i + 304) = 0;
    }
    CClassRecord::Release(v5);
    v6 = 0;
  }
  CInCritSec::~CInCritSec((CInCritSec *)&v13);
  return v6;
}

```

## disassembly

```asm
0x18003e1f0  mov     [rsp+arg_8], rbx
0x18003e1f5  push    rbp
0x18003e1f6  push    rsi
0x18003e1f7  push    rdi
0x18003e1f8  sub     rsp, 20h
0x18003e1fc  mov     rbx, rdx
0x18003e1ff  mov     rsi, rcx
0x18003e202  mov     rdx, [rcx+10h]
0x18003e206  lea     rcx, [rsp+38h+arg_0]
0x18003e20b  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18003e211  nop
0x18003e212  mov     rdx, rbx; unsigned __int16 *
0x18003e215  mov     rcx, rsi; this
0x18003e218  call    ?FindClass@CHierarchyCache@@IEAAPEAVCClassRecord@@PEBG@Z; CHierarchyCache::FindClass(ushort const *)
0x18003e21d  mov     rbx, rax
0x18003e220  mov     edi, 1
0x18003e225  test    rax, rax
0x18003e228  jz      loc_18003E2F5
0x18003e22e  lock add [rax+8], edi
0x18003e232  mov     [rsp+38h+arg_10], rax
0x18003e237  mov     rbp, [rsi+28h]
0x18003e23b  lea     rax, [rbp+1]
0x18003e23f  mov     [rsi+28h], rax
0x18003e243  mov     rdx, rbx; struct CClassRecord *
0x18003e246  mov     rcx, rsi; this
0x18003e249  call    ?InvalidateClassInternal@CHierarchyCache@@IEAAJPEAVCClassRecord@@@Z; CHierarchyCache::InvalidateClassInternal(CClassRecord *)
0x18003e24e  mov     rax, [rbx+0C0h]
0x18003e255  test    rax, rax
0x18003e258  jz      loc_18003E2EB
0x18003e25e  mov     byte ptr [rax+131h], 0
0x18003e265  mov     rax, [rbx+0C0h]
0x18003e26c  mov     byte ptr [rax+130h], 0
0x18003e273  mov     rax, [rbx+0C0h]
0x18003e27a  mov     [rax+138h], rbp
0x18003e281  xor     esi, esi
0x18003e283  mov     rbp, [rbx+0C0h]
0x18003e28a  add     rbp, 0D0h
0x18003e291  mov     rcx, rbp
0x18003e294  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18003e29a  cmp     esi, eax
0x18003e29c  jge     short loc_18003E2C8
0x18003e29e  mov     edx, esi
0x18003e2a0  mov     rcx, rbp
0x18003e2a3  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18003e2a9  cmp     rax, rbx
0x18003e2ac  jz      short loc_18003E2B2
0x18003e2ae  add     esi, edi
0x18003e2b0  jmp     short loc_18003E291
0x18003e2b2  mov     edx, esi
0x18003e2b4  mov     rcx, rbp
0x18003e2b7  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18003e2bd  mov     edx, esi
0x18003e2bf  mov     rcx, rbp
0x18003e2c2  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x18003e2c8  mov     rax, [rbx+0C0h]
0x18003e2cf  mov     rcx, [rax+0C0h]
0x18003e2d6  jmp     short loc_18003E2E6
0x18003e2d8  mov     byte ptr [rcx+130h], 0
0x18003e2df  mov     rcx, [rcx+0C0h]
0x18003e2e6  test    rcx, rcx
0x18003e2e9  jnz     short loc_18003E2D8
0x18003e2eb  mov     rcx, rbx; this
0x18003e2ee  call    ?Release@CClassRecord@@QEAAXXZ; CClassRecord::Release(void)
0x18003e2f3  xor     edi, edi
0x18003e2f5  lea     rcx, [rsp+38h+arg_0]
0x18003e2fa  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18003e300  mov     eax, edi
0x18003e302  mov     rbx, [rsp+38h+arg_8]
0x18003e307  add     rsp, 20h
0x18003e30b  pop     rdi
0x18003e30c  pop     rsi
0x18003e30d  pop     rbp
0x18003e30e  retn
```
