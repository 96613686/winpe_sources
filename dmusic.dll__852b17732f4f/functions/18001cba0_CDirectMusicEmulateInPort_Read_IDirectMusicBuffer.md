# CDirectMusicEmulateInPort::Read(IDirectMusicBuffer *)

- ea: `0x18001cba0`
- end: `0x18001cdf4`
- name: `?Read@CDirectMusicEmulateInPort@@UEAAJPEAUIDirectMusicBuffer@@@Z`
- size: `596`
- prototype: `__int64 __fastcall(CDirectMusicEmulateInPort *__hidden this, struct IDirectMusicBuffer *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001cba0`
- `0x1800217bc`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cd9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cd9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cc50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cc50`
- `api-ms-win-mm-mme-l1-1-0!midiInAddBuffer` at `0x18001cd31`
- `api-ms-win-mm-mme-l1-1-0!midiInAddBuffer` at `0x18001cd31`

## pseudocode

```c
__int64 __fastcall CDirectMusicEmulateInPort::Read(CDirectMusicEmulateInPort *this, struct IDirectMusicBuffer *a2)
{
  struct IDirectMusicBufferVtbl *lpVtbl; // rax
  __int64 result; // rax
  HRESULT (__stdcall *GetRawBufferPtr)(IDirectMusicBuffer *, LPBYTE *); // rax
  struct IDirectMusicBufferVtbl *v7; // rax
  __int64 v8; // r12
  struct _RTL_CRITICAL_SECTION *v9; // rbp
  __int64 v10; // rdi
  __int64 v11; // r9
  _DWORD *v12; // r14
  __int64 v13; // r8
  unsigned int v14; // ebp
  unsigned int v15; // eax
  struct midihdr_tag *v16; // r13
  const void *v17; // rdx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rax
  unsigned int v21; // [rsp+78h] [rbp+10h] BYREF
  __int64 v22; // [rsp+80h] [rbp+18h] BYREF
  __int64 v23; // [rsp+88h] [rbp+20h]

  if ( !a2 )
    return 2147500035LL;
  lpVtbl = a2->lpVtbl;
  if ( !a2->lpVtbl || !lpVtbl->QueryInterface )
    return 2147500035LL;
  if ( !*((_QWORD *)this + 46) )
    return 2289570100LL;
  GetRawBufferPtr = lpVtbl->GetRawBufferPtr;
  v22 = 0;
  result = ((__int64 (__fastcall *)(struct IDirectMusicBuffer *, __int64 *))GetRawBufferPtr)(a2, &v22);
  if ( (int)result >= 0 )
  {
    v7 = a2->lpVtbl;
    v21 = 0;
    result = ((__int64 (__fastcall *)(struct IDirectMusicBuffer *, unsigned int *))v7->GetMaxBytes)(a2, &v21);
    if ( (int)result >= 0 )
    {
      v8 = v22;
      v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 464);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 464));
      v10 = *((_QWORD *)this + 54);
      if ( v10 )
      {
        v11 = *(_QWORD *)(v10 + 16);
        v23 = v11;
        while ( v21 >= 0x18 )
        {
          v12 = (_DWORD *)(v10 + 72);
          if ( (*(_BYTE *)(v10 + 24) & 1) != 0 )
          {
            v13 = (unsigned int)*v12;
            v14 = *(_DWORD *)(v10 + 40) - v13;
            v15 = (v14 + 27) & 0xFFFFFFF8;
            if ( v15 > v21 )
              v14 -= (v15 - v21 + 7) & 0xFFFFFFF8;
            v16 = (struct midihdr_tag *)(v10 + 28);
            v17 = (const void *)(*(_QWORD *)(v10 + 28) + v13);
            *v12 = v13 + v14;
          }
          else
          {
            v14 = *(_DWORD *)(v10 + 8);
            v17 = (const void *)(v10 + 28);
            v16 = (struct midihdr_tag *)(v10 + 28);
          }
          *(_QWORD *)(v8 + 8) = *(_QWORD *)(v10 + 16) - v11;
          *(_DWORD *)v8 = v14;
          *(_DWORD *)(v8 + 16) = 0;
          *(_DWORD *)(v8 + 4) = 1;
          memcpy_0((void *)(v8 + 20), v17, v14);
          v18 = (v14 + 27) & 0xFFFFFFF8;
          v21 -= v18;
          v8 += v18;
          *((_QWORD *)this + 54) = *(_QWORD *)v10;
          if ( (*(_BYTE *)(v10 + 24) & 1) != 0 )
          {
            v19 = *(_DWORD *)(v10 + 40);
            *v12 = v19;
            if ( v19 )
            {
              _InterlockedIncrement((volatile signed __int32 *)this + 133);
              if ( midiInAddBuffer(*((HMIDIIN *)this + 64), v16, 0x70u) )
                _InterlockedDecrement((volatile signed __int32 *)this + 133);
            }
          }
          else
          {
            v20 = *((_QWORD *)this + 53);
            ++*((_DWORD *)this + 104);
            *(_QWORD *)v10 = v20;
            *((_QWORD *)this + 53) = v10;
          }
          v10 = *((_QWORD *)this + 54);
          v11 = v23;
          if ( !v10 )
          {
            v10 = v23;
            v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 464);
            goto LABEL_23;
          }
        }
        v10 = v23;
        v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 464);
      }
      else
      {
LABEL_23:
        *((_QWORD *)this + 55) = 0;
      }
      LeaveCriticalSection(v9);
      ((void (__fastcall *)(struct IDirectMusicBuffer *, __int64))a2->lpVtbl->SetStartTime)(a2, v10);
      ((void (__fastcall *)(struct IDirectMusicBuffer *, _QWORD))a2->lpVtbl->SetUsedBytes)(a2, (unsigned int)(v8 - v22));
      return v8 == v22;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001cba0  mov     [rsp+arg_0], rbx
0x18001cba5  push    rbp
0x18001cba6  push    rsi
0x18001cba7  push    rdi
0x18001cba8  push    r12
0x18001cbaa  push    r13
0x18001cbac  push    r14
0x18001cbae  push    r15
0x18001cbb0  sub     rsp, 30h
0x18001cbb4  mov     rsi, rdx
0x18001cbb7  mov     rbx, rcx
0x18001cbba  test    rdx, rdx
0x18001cbbd  jz      loc_18001CDDA
0x18001cbc3  mov     rax, [rdx]
0x18001cbc6  test    rax, rax
0x18001cbc9  jz      loc_18001CDDA
0x18001cbcf  cmp     qword ptr [rax], 0
0x18001cbd3  jz      loc_18001CDDA
0x18001cbd9  cmp     qword ptr [rcx+170h], 0
0x18001cbe1  jnz     short loc_18001CBED
0x18001cbe3  mov     eax, 88781134h
0x18001cbe8  jmp     loc_18001CDDF
0x18001cbed  mov     rax, [rax+48h]
0x18001cbf1  lea     rdx, [rsp+68h+arg_10]
0x18001cbf9  mov     rcx, rsi
0x18001cbfc  mov     [rsp+68h+arg_10], 0
0x18001cc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc0d  test    eax, eax
0x18001cc0f  js      loc_18001CDDF
0x18001cc15  mov     rax, [rsi]
0x18001cc18  lea     rdx, [rsp+68h+arg_8]
0x18001cc1d  mov     rcx, rsi
0x18001cc20  mov     [rsp+68h+arg_8], 0
0x18001cc28  mov     rax, [rax+60h]
0x18001cc2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc31  test    eax, eax
0x18001cc33  js      loc_18001CDDF
0x18001cc39  mov     r12, [rsp+68h+arg_10]
0x18001cc41  lea     rbp, [rbx+1D0h]
0x18001cc48  mov     rcx, rbp; lpCriticalSection
0x18001cc4b  mov     [rsp+68h+var_48], rbp
0x18001cc50  call    cs:__imp_EnterCriticalSection
0x18001cc56  mov     rdi, [rbx+1B0h]
0x18001cc5d  test    rdi, rdi
0x18001cc60  jz      loc_18001CD7D
0x18001cc66  mov     r9, [rdi+10h]
0x18001cc6a  mov     [rsp+68h+arg_18], r9
0x18001cc72  mov     ecx, [rsp+68h+arg_8]
0x18001cc76  cmp     ecx, 18h
0x18001cc79  jb      loc_18001CD8A
0x18001cc7f  test    byte ptr [rdi+18h], 1
0x18001cc83  lea     r14, [rdi+48h]
0x18001cc87  jz      short loc_18001CCBA
0x18001cc89  mov     r8d, [r14]
0x18001cc8c  mov     ebp, [rdi+28h]
0x18001cc8f  sub     ebp, r8d
0x18001cc92  lea     eax, [rbp+1Bh]
0x18001cc95  and     eax, 0FFFFFFF8h
0x18001cc98  cmp     eax, ecx
0x18001cc9a  jbe     short loc_18001CCA6
0x18001cc9c  sub     eax, ecx
0x18001cc9e  add     eax, 7
0x18001cca1  and     eax, 0FFFFFFF8h
0x18001cca4  sub     ebp, eax
0x18001cca6  lea     r13, [rdi+1Ch]
0x18001ccaa  mov     rdx, r8
0x18001ccad  add     rdx, [r13+0]
0x18001ccb1  lea     eax, [r8+rbp]
0x18001ccb5  mov     [r14], eax
0x18001ccb8  jmp     short loc_18001CCC4
0x18001ccba  mov     ebp, [rdi+8]
0x18001ccbd  lea     rdx, [rdi+1Ch]; Src
0x18001ccc1  mov     r13, rdx
0x18001ccc4  mov     rax, [rdi+10h]
0x18001ccc8  lea     rcx, [r12+14h]; void *
0x18001cccd  sub     rax, r9
0x18001ccd0  mov     r8d, ebp; Size
0x18001ccd3  mov     [r12+8], rax
0x18001ccd8  mov     [r12], ebp
0x18001ccdc  mov     dword ptr [r12+10h], 0
0x18001cce5  mov     dword ptr [r12+4], 1
0x18001ccee  call    memcpy_0
0x18001ccf3  lea     ecx, [rbp+1Bh]
0x18001ccf6  and     ecx, 0FFFFFFF8h
0x18001ccf9  sub     [rsp+68h+arg_8], ecx
0x18001ccfd  add     r12, rcx
0x18001cd00  mov     rax, [rdi]
0x18001cd03  mov     [rbx+1B0h], rax
0x18001cd0a  test    byte ptr [rdi+18h], 1
0x18001cd0e  jz      short loc_18001CD44
0x18001cd10  mov     eax, [rdi+28h]
0x18001cd13  mov     [r14], eax
0x18001cd16  test    eax, eax
0x18001cd18  jz      short loc_18001CD5B
0x18001cd1a  lock inc dword ptr [rbx+214h]
0x18001cd21  mov     rcx, [rbx+200h]; hmi
0x18001cd28  mov     r8d, 70h ; 'p'; cbmh
0x18001cd2e  mov     rdx, r13; pmh
0x18001cd31  call    cs:__imp_midiInAddBuffer
0x18001cd37  test    eax, eax
0x18001cd39  jz      short loc_18001CD5B
0x18001cd3b  lock dec dword ptr [rbx+214h]
0x18001cd42  jmp     short loc_18001CD5B
0x18001cd44  mov     rax, [rbx+1A8h]
0x18001cd4b  inc     dword ptr [rbx+1A0h]
0x18001cd51  mov     [rdi], rax
0x18001cd54  mov     [rbx+1A8h], rdi
0x18001cd5b  mov     rdi, [rbx+1B0h]
0x18001cd62  mov     r9, [rsp+68h+arg_18]
0x18001cd6a  test    rdi, rdi
0x18001cd6d  jnz     loc_18001CC72
0x18001cd73  mov     rdi, r9
0x18001cd76  lea     rbp, [rbx+1D0h]
0x18001cd7d  mov     qword ptr [rbx+1B8h], 0
0x18001cd88  jmp     short loc_18001CD97
0x18001cd8a  mov     rdi, [rsp+68h+arg_18]
0x18001cd92  mov     rbp, [rsp+68h+var_48]
0x18001cd97  mov     rcx, rbp; lpCriticalSection
0x18001cd9a  call    cs:__imp_LeaveCriticalSection
0x18001cda0  mov     rax, [rsi]
0x18001cda3  mov     rdx, rdi
0x18001cda6  mov     rcx, rsi
0x18001cda9  mov     rax, [rax+70h]
0x18001cdad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdb2  mov     rax, [rsi]
0x18001cdb5  mov     edx, r12d
0x18001cdb8  sub     edx, dword ptr [rsp+68h+arg_10]
0x18001cdbf  mov     rcx, rsi
0x18001cdc2  mov     rax, [rax+78h]
0x18001cdc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdcb  xor     eax, eax
0x18001cdcd  cmp     r12, [rsp+68h+arg_10]
0x18001cdd5  setz    al
0x18001cdd8  jmp     short loc_18001CDDF
0x18001cdda  mov     eax, 80004003h
0x18001cddf  mov     rbx, [rsp+68h+arg_0]
0x18001cde4  add     rsp, 30h
0x18001cde8  pop     r15
0x18001cdea  pop     r14
0x18001cdec  pop     r13
0x18001cdee  pop     r12
0x18001cdf0  pop     rdi
0x18001cdf1  pop     rsi
0x18001cdf2  pop     rbp
0x18001cdf3  retn
```
