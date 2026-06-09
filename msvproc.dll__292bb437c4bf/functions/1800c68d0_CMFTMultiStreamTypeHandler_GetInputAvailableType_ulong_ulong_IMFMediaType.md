# CMFTMultiStreamTypeHandler::GetInputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x1800c68d0`
- end: `0x1800c6a1e`
- name: `?GetInputAvailableType@CMFTMultiStreamTypeHandler@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(CMFTMultiStreamTypeHandler *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001e920`

## callees

- `0x1800c68d0`
- `0x1800c7380`
- `0x1800c7ba4`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c68fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c68fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c69ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c69ff`
- `MFPlat!MFCreateMediaType` at `0x1800c69ae`
- `MFPlat!MFCreateMediaType` at `0x1800c69ae`

## pseudocode

```c
__int64 __fastcall CMFTMultiStreamTypeHandler::GetInputAvailableType(
        CMFTMultiStreamTypeHandler *this,
        unsigned int a2,
        int a3,
        struct IMFMediaType **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  HRESULT v9; // edi
  __int64 v10; // rdi
  __int64 v11; // r15
  __int64 v12; // rbp
  __int64 v13; // r9
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  int v16; // r8d
  unsigned int v17; // edx
  __int64 v18; // rsi
  __int64 v19; // rcx
  unsigned int v21; // [rsp+50h] [rbp+8h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 304);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  v21 = 0;
  v9 = CMFTMultiStreamTypeHandler::InputStreamIdToStreamIndex(this, a2, &v21);
  if ( v9 < 0 )
    goto LABEL_22;
  v10 = v21;
  if ( v21 >= *((_DWORD *)this + 73) )
  {
    v9 = -1072875853;
    goto LABEL_22;
  }
  if ( !a4 )
  {
    v9 = -2147467261;
    goto LABEL_22;
  }
  if ( *((_DWORD *)this + 69) == 1 && !(unsigned int)CMFTMultiStreamTypeHandler::IsAnyOutputTypeSet(this) )
  {
    v9 = -1072861856;
    goto LABEL_22;
  }
  v11 = *((_QWORD *)this + 2);
  v12 = 3 * v10;
  v13 = *(_QWORD *)(v11 + 24 * v10);
  v14 = *(_QWORD *)(v11 + 24 * v10 + 8) - v13;
  if ( !v14 || (v15 = v14 >> 4) == 0 )
  {
LABEL_9:
    v9 = -1072875847;
    goto LABEL_22;
  }
  v16 = 0;
  v17 = 0;
  while ( 1 )
  {
    v18 = 2LL * v17;
    if ( *(_DWORD *)(v13 + 16LL * v17 + 8) )
      break;
LABEL_15:
    if ( ++v17 >= v15 )
      goto LABEL_9;
  }
  if ( v16 != a3 )
  {
    ++v16;
    goto LABEL_15;
  }
  v9 = MFCreateMediaType(a4);
  if ( v9 >= 0 )
  {
    v19 = *(_QWORD *)(*(_QWORD *)(v11 + 8 * v12) + 8 * v18);
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 256LL))(v19, *a4);
    if ( v9 < 0 )
    {
      if ( *a4 )
      {
        ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
        *a4 = 0;
      }
    }
  }
LABEL_22:
  LeaveCriticalSection(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800c68d0  mov     [rsp+arg_8], rbx
0x1800c68d5  mov     [rsp+arg_10], rbp
0x1800c68da  push    rsi
0x1800c68db  push    rdi
0x1800c68dc  push    r12
0x1800c68de  push    r14
0x1800c68e0  push    r15
0x1800c68e2  sub     rsp, 20h
0x1800c68e6  lea     rbx, [rcx+130h]
0x1800c68ed  mov     rsi, rcx
0x1800c68f0  mov     rcx, rbx; lpCriticalSection
0x1800c68f3  mov     r14, r9
0x1800c68f6  mov     r12d, r8d
0x1800c68f9  mov     edi, edx
0x1800c68fb  call    cs:__imp_EnterCriticalSection
0x1800c6901  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x1800c6906  mov     [rsp+48h+arg_0], 0
0x1800c690e  mov     edx, edi; unsigned int
0x1800c6910  mov     rcx, rsi; this
0x1800c6913  call    ?InputStreamIdToStreamIndex@CMFTMultiStreamTypeHandler@@QEAAJKPEAK@Z; CMFTMultiStreamTypeHandler::InputStreamIdToStreamIndex(ulong,ulong *)
0x1800c6918  mov     edi, eax
0x1800c691a  test    eax, eax
0x1800c691c  js      loc_1800C69FC
0x1800c6922  mov     edi, [rsp+48h+arg_0]
0x1800c6926  cmp     edi, [rsi+124h]
0x1800c692c  jnb     loc_1800C69F7
0x1800c6932  test    r14, r14
0x1800c6935  jnz     short loc_1800C6941
0x1800c6937  mov     edi, 80004003h
0x1800c693c  jmp     loc_1800C69FC
0x1800c6941  cmp     dword ptr [rsi+114h], 1
0x1800c6948  jnz     short loc_1800C6960
0x1800c694a  mov     rcx, rsi; this
0x1800c694d  call    ?IsAnyOutputTypeSet@CMFTMultiStreamTypeHandler@@QEAAHXZ; CMFTMultiStreamTypeHandler::IsAnyOutputTypeSet(void)
0x1800c6952  test    eax, eax
0x1800c6954  jnz     short loc_1800C6960
0x1800c6956  mov     edi, 0C00D6D60h
0x1800c695b  jmp     loc_1800C69FC
0x1800c6960  mov     r15, [rsi+10h]
0x1800c6964  lea     rbp, [rdi+rdi*2]
0x1800c6968  mov     r9, [r15+rbp*8]
0x1800c696c  mov     rcx, [r15+rbp*8+8]
0x1800c6971  sub     rcx, r9
0x1800c6974  jnz     short loc_1800C697D
0x1800c6976  mov     edi, 0C00D36B9h
0x1800c697b  jmp     short loc_1800C69FC
0x1800c697d  sar     rcx, 4
0x1800c6981  test    rcx, rcx
0x1800c6984  jz      short loc_1800C6976
0x1800c6986  xor     r8d, r8d
0x1800c6989  xor     edx, edx
0x1800c698b  mov     esi, edx
0x1800c698d  add     rsi, rsi
0x1800c6990  cmp     dword ptr [r9+rsi*8+8], 0
0x1800c6996  jz      short loc_1800C69A0
0x1800c6998  cmp     r8d, r12d
0x1800c699b  jz      short loc_1800C69AB
0x1800c699d  inc     r8d
0x1800c69a0  inc     edx
0x1800c69a2  mov     eax, edx
0x1800c69a4  cmp     rax, rcx
0x1800c69a7  jb      short loc_1800C698B
0x1800c69a9  jmp     short loc_1800C6976
0x1800c69ab  mov     rcx, r14; ppMFType
0x1800c69ae  call    cs:__imp_MFCreateMediaType
0x1800c69b4  mov     edi, eax
0x1800c69b6  test    eax, eax
0x1800c69b8  js      short loc_1800C69FC
0x1800c69ba  mov     rax, [r15+rbp*8]
0x1800c69be  mov     rdx, [r14]
0x1800c69c1  mov     rcx, [rax+rsi*8]
0x1800c69c5  mov     rax, [rcx]
0x1800c69c8  mov     rax, [rax+100h]
0x1800c69cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c69d4  mov     edi, eax
0x1800c69d6  test    eax, eax
0x1800c69d8  jns     short loc_1800C69FC
0x1800c69da  mov     rcx, [r14]
0x1800c69dd  test    rcx, rcx
0x1800c69e0  jz      short loc_1800C69FC
0x1800c69e2  mov     rax, [rcx]
0x1800c69e5  mov     rax, [rax+10h]
0x1800c69e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c69ee  mov     qword ptr [r14], 0
0x1800c69f5  jmp     short loc_1800C69FC
0x1800c69f7  mov     edi, 0C00D36B3h
0x1800c69fc  mov     rcx, rbx; lpCriticalSection
0x1800c69ff  call    cs:__imp_LeaveCriticalSection
0x1800c6a05  mov     rbx, [rsp+48h+arg_8]
0x1800c6a0a  mov     eax, edi
0x1800c6a0c  mov     rbp, [rsp+48h+arg_10]
0x1800c6a11  add     rsp, 20h
0x1800c6a15  pop     r15
0x1800c6a17  pop     r14
0x1800c6a19  pop     r12
0x1800c6a1b  pop     rdi
0x1800c6a1c  pop     rsi
0x1800c6a1d  retn
```
