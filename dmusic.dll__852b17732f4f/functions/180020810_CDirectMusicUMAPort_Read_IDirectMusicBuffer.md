# CDirectMusicUMAPort::Read(IDirectMusicBuffer *)

- ea: `0x180020810`
- end: `0x1800209a8`
- name: `?Read@CDirectMusicUMAPort@@UEAAJPEAUIDirectMusicBuffer@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(CDirectMusicUMAPort *__hidden this, struct IDirectMusicBuffer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800012c4`
- `0x180020810`
- `0x1800217bc`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020954`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020954`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800208bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800208bf`

## pseudocode

```c
__int64 __fastcall CDirectMusicUMAPort::Read(CDirectMusicUMAPort *this, struct IDirectMusicBuffer *a2)
{
  struct IDirectMusicBufferVtbl *lpVtbl; // rax
  __int64 result; // rax
  HRESULT (__stdcall *GetRawBufferPtr)(IDirectMusicBuffer *, LPBYTE *); // rax
  struct IDirectMusicBufferVtbl *v7; // rax
  char *v8; // r12
  _QWORD *v9; // rdi
  __int64 v10; // r15
  __int64 v11; // rax
  unsigned int v12; // ebp
  __int64 v13; // rax
  unsigned int v14; // [rsp+68h] [rbp+10h] BYREF
  void *v15; // [rsp+70h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  lpVtbl = a2->lpVtbl;
  if ( !a2->lpVtbl || !lpVtbl->QueryInterface )
    return 2147500035LL;
  if ( !*((_QWORD *)this + 5) )
    return 2289570100LL;
  if ( *((_DWORD *)this + 12) )
    return 2147500033LL;
  GetRawBufferPtr = lpVtbl->GetRawBufferPtr;
  v15 = 0;
  result = ((__int64 (__fastcall *)(struct IDirectMusicBuffer *, void **))GetRawBufferPtr)(a2, &v15);
  if ( (int)result >= 0 )
  {
    v7 = a2->lpVtbl;
    v14 = 0;
    result = ((__int64 (__fastcall *)(struct IDirectMusicBuffer *, unsigned int *))v7->GetMaxBytes)(a2, &v14);
    if ( (int)result >= 0 )
    {
      v8 = (char *)v15;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1176));
      v9 = (_QWORD *)*((_QWORD *)this + 145);
      if ( v9 )
      {
        v10 = v9[2];
        while ( 1 )
        {
          v11 = *((unsigned int *)v9 + 2);
          v12 = (v11 + 27) & 0xFFFFFFF8;
          if ( v12 > v14 )
            break;
          v9[2] -= v10;
          memcpy_0(v8, v9 + 1, v11 + 20);
          v14 -= v12;
          v8 += v12;
          *((_QWORD *)this + 145) = *v9;
          if ( *((_DWORD *)v9 + 2) > 4u )
          {
            operator delete(v9);
          }
          else
          {
            v13 = *((_QWORD *)this + 144);
            ++*((_DWORD *)this + 286);
            *v9 = v13;
            *((_QWORD *)this + 144) = v9;
          }
          v9 = (_QWORD *)*((_QWORD *)this + 145);
          if ( !v9 )
            goto LABEL_19;
        }
      }
      else
      {
        v10 = 0;
LABEL_19:
        *((_QWORD *)this + 146) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1176));
      ((void (__fastcall *)(struct IDirectMusicBuffer *, __int64))a2->lpVtbl->SetStartTime)(a2, v10);
      ((void (__fastcall *)(struct IDirectMusicBuffer *, _QWORD))a2->lpVtbl->SetUsedBytes)(
        a2,
        (unsigned int)((_DWORD)v8 - (_DWORD)v15));
      return v8 == v15;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180020810  mov     [rsp+arg_0], rbx
0x180020815  push    rbp
0x180020816  push    rsi
0x180020817  push    rdi
0x180020818  push    r12
0x18002081a  push    r13
0x18002081c  push    r14
0x18002081e  push    r15
0x180020820  sub     rsp, 20h
0x180020824  mov     rsi, rdx
0x180020827  mov     rbx, rcx
0x18002082a  test    rdx, rdx
0x18002082d  jz      loc_18002098E
0x180020833  mov     rax, [rdx]
0x180020836  test    rax, rax
0x180020839  jz      loc_18002098E
0x18002083f  cmp     qword ptr [rax], 0
0x180020843  jz      loc_18002098E
0x180020849  cmp     qword ptr [rcx+28h], 0
0x18002084e  jnz     short loc_18002085A
0x180020850  mov     eax, 88781134h
0x180020855  jmp     loc_180020993
0x18002085a  cmp     dword ptr [rcx+30h], 0
0x18002085e  jz      short loc_18002086A
0x180020860  mov     eax, 80004001h
0x180020865  jmp     loc_180020993
0x18002086a  mov     rax, [rax+48h]
0x18002086e  lea     rdx, [rsp+58h+arg_10]
0x180020873  mov     rcx, rsi
0x180020876  mov     [rsp+58h+arg_10], 0
0x18002087f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020884  test    eax, eax
0x180020886  js      loc_180020993
0x18002088c  mov     rax, [rsi]
0x18002088f  lea     rdx, [rsp+58h+arg_8]
0x180020894  mov     rcx, rsi
0x180020897  mov     [rsp+58h+arg_8], 0
0x18002089f  mov     rax, [rax+60h]
0x1800208a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208a8  test    eax, eax
0x1800208aa  js      loc_180020993
0x1800208b0  mov     r12, [rsp+58h+arg_10]
0x1800208b5  lea     r13, [rbx+498h]
0x1800208bc  mov     rcx, r13; lpCriticalSection
0x1800208bf  call    cs:__imp_EnterCriticalSection
0x1800208c5  mov     rdi, [rbx+488h]
0x1800208cc  test    rdi, rdi
0x1800208cf  jz      short loc_180020943
0x1800208d1  mov     r15, [rdi+10h]
0x1800208d5  lea     r14, [rdi+8]
0x1800208d9  mov     eax, [r14]
0x1800208dc  lea     ebp, [rax+1Bh]
0x1800208df  and     ebp, 0FFFFFFF8h
0x1800208e2  cmp     ebp, [rsp+58h+arg_8]
0x1800208e6  ja      short loc_180020951
0x1800208e8  sub     [rdi+10h], r15
0x1800208ec  lea     r8, [rax+14h]; Size
0x1800208f0  mov     rdx, r14; Src
0x1800208f3  mov     rcx, r12; void *
0x1800208f6  call    memcpy_0
0x1800208fb  sub     [rsp+58h+arg_8], ebp
0x1800208ff  mov     eax, ebp
0x180020901  add     r12, rax
0x180020904  mov     rax, [rdi]
0x180020907  mov     [rbx+488h], rax
0x18002090e  cmp     dword ptr [r14], 4
0x180020912  ja      short loc_18002092D
0x180020914  mov     rax, [rbx+480h]
0x18002091b  inc     dword ptr [rbx+478h]
0x180020921  mov     [rdi], rax
0x180020924  mov     [rbx+480h], rdi
0x18002092b  jmp     short loc_180020935
0x18002092d  mov     rcx, rdi; void *
0x180020930  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020935  mov     rdi, [rbx+488h]
0x18002093c  test    rdi, rdi
0x18002093f  jnz     short loc_1800208D5
0x180020941  jmp     short loc_180020946
0x180020943  xor     r15d, r15d
0x180020946  mov     qword ptr [rbx+490h], 0
0x180020951  mov     rcx, r13; lpCriticalSection
0x180020954  call    cs:__imp_LeaveCriticalSection
0x18002095a  mov     rax, [rsi]
0x18002095d  mov     rdx, r15
0x180020960  mov     rcx, rsi
0x180020963  mov     rax, [rax+70h]
0x180020967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002096c  mov     rax, [rsi]
0x18002096f  mov     edx, r12d
0x180020972  sub     edx, dword ptr [rsp+58h+arg_10]
0x180020976  mov     rcx, rsi
0x180020979  mov     rax, [rax+78h]
0x18002097d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020982  xor     eax, eax
0x180020984  cmp     r12, [rsp+58h+arg_10]
0x180020989  setz    al
0x18002098c  jmp     short loc_180020993
0x18002098e  mov     eax, 80004003h
0x180020993  mov     rbx, [rsp+58h+arg_0]
0x180020998  add     rsp, 20h
0x18002099c  pop     r15
0x18002099e  pop     r14
0x1800209a0  pop     r13
0x1800209a2  pop     r12
0x1800209a4  pop     rdi
0x1800209a5  pop     rsi
0x1800209a6  pop     rbp
0x1800209a7  retn
```
