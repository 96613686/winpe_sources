# CKsOutputPin2::GetStreamCaps(int,_AMMediaType * *,uchar *)

- ea: `0x18002fa50`
- end: `0x18002fb93`
- name: `?GetStreamCaps@CKsOutputPin2@@UEAAJHPEAPEAU_AMMediaType@@PEAE@Z`
- size: `323`
- prototype: `__int64 __fastcall(CKsOutputPin *this, int, struct _AMMediaType **, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x1800043d0`
- `0x18001ffb0`
- `0x18002dcc8`
- `0x18002dd70`
- `0x18002fa50`
- `0x18003e22c`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18002fabd`
- `ole32!CoTaskMemAlloc` at `0x18002fabd`

## pseudocode

```c
__int64 __fastcall CKsOutputPin2::GetStreamCaps(
        CKsOutputPin *this,
        int a2,
        struct _AMMediaType **a3,
        unsigned __int8 *a4)
{
  __int64 v5; // rbp
  unsigned int *p_Id; // rcx
  __int64 result; // rax
  struct _AMMediaType *v10; // rax
  int v11; // r14d
  CBaseList::CNode *m_pHead; // rcx
  _OWORD *v13; // rdx

  v5 = a2;
  p_Id = &this[-1].m_CurrentInterface.Id;
  if ( p_Id[300] || (result = CKsOutputPin2::CreateMediaTypeArrays((CKsOutputPin2 *)p_Id), (int)result >= 0) )
  {
    if ( this->m_MarshalerList.m_Cache.m_iCacheSize )
    {
      if ( (int)v5 < SLODWORD(this->m_IoCriticalSection.m_CritSec.DebugInfo) )
      {
        v10 = (struct _AMMediaType *)CoTaskMemAlloc(0x58u);
        *a3 = v10;
        if ( v10 )
        {
          memset_0((void *)v10, 0, sizeof(struct _AMMediaType));
          v11 = ConvertKsMediaTypeToAmMediaType(
                  *(union KSDATAFORMAT **)(*(_QWORD *)&this->m_IoQueue.m_Cache.m_iCacheSize + 8 * v5),
                  *a3);
          if ( v11 < 0 )
          {
            DeleteMediaType(*a3);
            *a3 = 0;
          }
          else
          {
            m_pHead = this->m_IoQueue.m_Cache.m_pHead;
            if ( m_pHead && *((_QWORD *)&m_pHead->m_pPrev + v5) )
            {
              _mm_lfence();
              v13 = (_OWORD *)*((_QWORD *)&this->m_IoQueue.m_Cache.m_pHead->m_pPrev + v5);
              *(_OWORD *)a4 = *v13;
              *((_OWORD *)a4 + 1) = v13[1];
              *((_OWORD *)a4 + 2) = v13[2];
              *((_OWORD *)a4 + 3) = v13[3];
              *((_OWORD *)a4 + 4) = v13[4];
              *((_OWORD *)a4 + 5) = v13[5];
              *((_OWORD *)a4 + 6) = v13[6];
              *((_OWORD *)a4 + 7) = v13[7];
            }
            else
            {
              memset_0(a4, 0, 0x80u);
            }
          }
          return (unsigned int)v11;
        }
        else
        {
          return 2147942414LL;
        }
      }
      else
      {
        return 1;
      }
    }
    else
    {
      return CKsOutputPin::GetStreamCaps(this, v5, a3, (GUID *)a4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002fa50  push    rbx
0x18002fa52  push    rbp
0x18002fa53  push    rsi
0x18002fa54  push    rdi
0x18002fa55  push    r14
0x18002fa57  sub     rsp, 20h
0x18002fa5b  mov     rbx, rcx
0x18002fa5e  movsxd  rbp, edx
0x18002fa61  add     rcx, 0FFFFFFFFFFFFFE48h; this
0x18002fa68  mov     rdi, r9
0x18002fa6b  mov     rsi, r8
0x18002fa6e  cmp     dword ptr [rcx+4B0h], 0
0x18002fa75  jnz     short loc_18002FA84
0x18002fa77  call    ?CreateMediaTypeArrays@CKsOutputPin2@@QEAAJXZ; CKsOutputPin2::CreateMediaTypeArrays(void)
0x18002fa7c  test    eax, eax
0x18002fa7e  js      loc_18002FB87
0x18002fa84  cmp     dword ptr [rbx+2C0h], 0
0x18002fa8b  jnz     short loc_18002FAA2
0x18002fa8d  mov     r9, rdi; unsigned __int8 *
0x18002fa90  mov     r8, rsi; struct _AMMediaType **
0x18002fa93  mov     edx, ebp; int
0x18002fa95  mov     rcx, rbx; this
0x18002fa98  call    ?GetStreamCaps@CKsOutputPin@@UEAAJHPEAPEAU_AMMediaType@@PEAE@Z; CKsOutputPin::GetStreamCaps(int,_AMMediaType * *,uchar *)
0x18002fa9d  jmp     loc_18002FB87
0x18002faa2  cmp     ebp, [rbx+2F8h]
0x18002faa8  jl      short loc_18002FAB4
0x18002faaa  mov     eax, 1
0x18002faaf  jmp     loc_18002FB87
0x18002fab4  mov     r14d, 58h ; 'X'
0x18002faba  mov     ecx, r14d; cb
0x18002fabd  call    cs:__imp_CoTaskMemAlloc
0x18002fac4  nop     dword ptr [rax+rax+00h]
0x18002fac9  mov     [rsi], rax
0x18002facc  test    rax, rax
0x18002facf  jnz     short loc_18002FADB
0x18002fad1  mov     eax, 8007000Eh
0x18002fad6  jmp     loc_18002FB87
0x18002fadb  mov     r8, r14; Size
0x18002fade  xor     edx, edx; Val
0x18002fae0  mov     rcx, rax; void *
0x18002fae3  call    memset_0
0x18002fae8  mov     rcx, [rbx+2E8h]
0x18002faef  mov     rdx, [rsi]; struct _AMMediaType *
0x18002faf2  mov     rcx, [rcx+rbp*8]; union KSDATAFORMAT *
0x18002faf6  call    ?ConvertKsMediaTypeToAmMediaType@@YAJPEATKSDATAFORMAT@@PEAU_AMMediaType@@@Z; ConvertKsMediaTypeToAmMediaType(KSDATAFORMAT *,_AMMediaType *)
0x18002fafb  mov     r14d, eax
0x18002fafe  test    eax, eax
0x18002fb00  js      short loc_18002FB75
0x18002fb02  mov     rcx, [rbx+2F0h]
0x18002fb09  test    rcx, rcx
0x18002fb0c  jz      short loc_18002FB63
0x18002fb0e  cmp     qword ptr [rcx+rbp*8], 0
0x18002fb13  jz      short loc_18002FB63
0x18002fb15  lfence
0x18002fb18  mov     rcx, [rbx+2F0h]
0x18002fb1f  mov     rdx, [rcx+rbp*8]
0x18002fb23  movups  xmm0, xmmword ptr [rdx]
0x18002fb26  movups  xmmword ptr [rdi], xmm0
0x18002fb29  movups  xmm1, xmmword ptr [rdx+10h]
0x18002fb2d  movups  xmmword ptr [rdi+10h], xmm1
0x18002fb31  movups  xmm0, xmmword ptr [rdx+20h]
0x18002fb35  movups  xmmword ptr [rdi+20h], xmm0
0x18002fb39  movups  xmm1, xmmword ptr [rdx+30h]
0x18002fb3d  movups  xmmword ptr [rdi+30h], xmm1
0x18002fb41  movups  xmm0, xmmword ptr [rdx+40h]
0x18002fb45  movups  xmmword ptr [rdi+40h], xmm0
0x18002fb49  movups  xmm1, xmmword ptr [rdx+50h]
0x18002fb4d  movups  xmmword ptr [rdi+50h], xmm1
0x18002fb51  movups  xmm0, xmmword ptr [rdx+60h]
0x18002fb55  movups  xmmword ptr [rdi+60h], xmm0
0x18002fb59  movups  xmm1, xmmword ptr [rdx+70h]
0x18002fb5d  movups  xmmword ptr [rdi+70h], xmm1
0x18002fb61  jmp     short loc_18002FB84
0x18002fb63  xor     edx, edx; Val
0x18002fb65  mov     r8d, 80h; Size
0x18002fb6b  mov     rcx, rdi; void *
0x18002fb6e  call    memset_0
0x18002fb73  jmp     short loc_18002FB84
0x18002fb75  mov     rcx, [rsi]; pv
0x18002fb78  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x18002fb7d  mov     qword ptr [rsi], 0
0x18002fb84  mov     eax, r14d
0x18002fb87  add     rsp, 20h
0x18002fb8b  pop     r14
0x18002fb8d  pop     rdi
0x18002fb8e  pop     rsi
0x18002fb8f  pop     rbp
0x18002fb90  pop     rbx
0x18002fb91  retn
```
