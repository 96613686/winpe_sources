# DoICM_DecompressX

- ea: `0x1800072f4`
- end: `0x18000745e`
- name: `DoICM_DecompressX`
- size: `362`
- prototype: `__int64 __fastcall(HIC hic, UINT msg)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800076c4`

## callees

- `0x180001d62`
- `0x180003a60`
- `0x180007084`
- `0x1800072f4`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007377`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000743c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000744b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007377`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000743c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000744b`

## pseudocode

```c
__int64 __fastcall DoICM_DecompressX(HIC hic, UINT msg, unsigned int a3, DWORD_PTR a4)
{
  HIC v4; // r14
  __int64 v8; // rbx
  unsigned int v10; // ebx
  DWORD_PTR dw1; // [rsp+20h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-48h]
  __int64 v13; // [rsp+30h] [rbp-40h]
  HLOCAL v14; // [rsp+38h] [rbp-38h]
  __int64 v15; // [rsp+40h] [rbp-30h]
  int v16; // [rsp+48h] [rbp-28h]
  int v17; // [rsp+4Ch] [rbp-24h]
  int v18; // [rsp+50h] [rbp-20h]
  int v19; // [rsp+54h] [rbp-1Ch]
  int v20; // [rsp+58h] [rbp-18h]
  int v21; // [rsp+5Ch] [rbp-14h]
  int v22; // [rsp+60h] [rbp-10h]
  int v23; // [rsp+64h] [rbp-Ch]

  v4 = (HIC)(unsigned int)hic;
  HIDWORD(dw1) = 0;
  memset_0(&dw1, 0, 0x44u);
  v8 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))GetVDMPointer)(a3, (unsigned int)a4, 1);
  LODWORD(dw1) = *(_DWORD *)v8;
  hMem = CopyBitmapInfo(*(unsigned int *)(v8 + 8));
  if ( !hMem )
    return 4294967293LL;
  v14 = CopyBitmapInfo(*(unsigned int *)(v8 + 24));
  if ( v14 )
  {
    if ( msg == 16446 || msg == 16397 )
    {
      v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))GetVDMPointer)(
              *(unsigned int *)(v8 + 16),
              *((unsigned int *)hMem + 5),
              1);
      v15 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))GetVDMPointer)(
              *(unsigned int *)(v8 + 32),
              *((unsigned int *)v14 + 5),
              1);
      goto LABEL_10;
    }
  }
  else if ( msg != 16445 )
  {
    LocalFree(hMem);
    return 4294967293LL;
  }
  v13 = 0;
  v15 = 0;
LABEL_10:
  if ( a4 == 56 )
  {
    a4 = 72;
    v16 = *(__int16 *)(v8 + 40);
    v17 = *(__int16 *)(v8 + 42);
    v18 = *(__int16 *)(v8 + 44);
    v19 = *(__int16 *)(v8 + 46);
    v20 = *(__int16 *)(v8 + 48);
    v21 = *(__int16 *)(v8 + 50);
    v22 = *(__int16 *)(v8 + 52);
    v23 = *(__int16 *)(v8 + 54);
  }
  v10 = ICSendMessage(v4, msg, (DWORD_PTR)&dw1, a4);
  LocalFree(hMem);
  if ( v14 )
    LocalFree(v14);
  return v10;
}

```

## disassembly

```asm
0x1800072f4  push    rbp
0x1800072f6  push    rbx
0x1800072f7  push    rsi
0x1800072f8  push    rdi
0x1800072f9  push    r14
0x1800072fb  mov     rbp, rsp
0x1800072fe  sub     rsp, 70h
0x180007302  xor     eax, eax
0x180007304  mov     r14d, ecx
0x180007307  mov     rbx, r8
0x18000730a  mov     dword ptr [rbp+dw1+4], eax
0x18000730d  mov     edi, edx
0x18000730f  lea     rcx, [rbp+dw1]; void *
0x180007313  xor     edx, edx; Val
0x180007315  mov     rsi, r9
0x180007318  lea     r8d, [rax+44h]; Size
0x18000731c  call    memset_0
0x180007321  mov     rax, cs:GetVDMPointer
0x180007328  mov     edx, esi
0x18000732a  mov     ecx, ebx
0x18000732c  mov     r8d, 1
0x180007332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007337  mov     rbx, rax
0x18000733a  mov     ecx, [rax]
0x18000733c  mov     dword ptr [rbp+dw1], ecx
0x18000733f  mov     ecx, [rax+8]
0x180007342  call    CopyBitmapInfo
0x180007347  mov     [rbp+hMem], rax
0x18000734b  test    rax, rax
0x18000734e  jnz     short loc_18000735A
0x180007350  mov     eax, 0FFFFFFFDh
0x180007355  jmp     loc_180007453
0x18000735a  mov     ecx, [rbx+18h]
0x18000735d  call    CopyBitmapInfo
0x180007362  mov     [rbp+var_38], rax
0x180007366  test    rax, rax
0x180007369  jnz     short loc_18000737F
0x18000736b  cmp     edi, 403Dh
0x180007371  jz      short loc_18000738F
0x180007373  mov     rcx, [rbp+hMem]; hMem
0x180007377  call    cs:__imp_LocalFree
0x18000737d  jmp     short loc_180007350
0x18000737f  cmp     edi, 403Eh
0x180007385  jz      short loc_1800073A1
0x180007387  cmp     edi, 400Dh
0x18000738d  jz      short loc_1800073A1
0x18000738f  mov     [rbp+var_40], 0
0x180007397  mov     [rbp+var_30], 0
0x18000739f  jmp     short loc_1800073E1
0x1800073a1  mov     rdx, [rbp+hMem]
0x1800073a5  mov     r8d, 1
0x1800073ab  mov     ecx, [rbx+10h]
0x1800073ae  mov     rax, cs:GetVDMPointer
0x1800073b5  mov     edx, [rdx+14h]
0x1800073b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073bd  mov     rdx, [rbp+var_38]
0x1800073c1  mov     r8d, 1
0x1800073c7  mov     [rbp+var_40], rax
0x1800073cb  mov     ecx, [rbx+20h]
0x1800073ce  mov     rax, cs:GetVDMPointer
0x1800073d5  mov     edx, [rdx+14h]
0x1800073d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073dd  mov     [rbp+var_30], rax
0x1800073e1  cmp     rsi, 38h ; '8'
0x1800073e5  jnz     short loc_180007424
0x1800073e7  movsx   eax, word ptr [rbx+28h]
0x1800073eb  mov     esi, 48h ; 'H'
0x1800073f0  mov     [rbp+var_28], eax
0x1800073f3  movsx   eax, word ptr [rbx+2Ah]
0x1800073f7  mov     [rbp+var_24], eax
0x1800073fa  movsx   eax, word ptr [rbx+2Ch]
0x1800073fe  mov     [rbp+var_20], eax
0x180007401  movsx   eax, word ptr [rbx+2Eh]
0x180007405  mov     [rbp+var_1C], eax
0x180007408  movsx   eax, word ptr [rbx+30h]
0x18000740c  mov     [rbp+var_18], eax
0x18000740f  movsx   eax, word ptr [rbx+32h]
0x180007413  mov     [rbp+var_14], eax
0x180007416  movsx   eax, word ptr [rbx+34h]
0x18000741a  mov     [rbp+var_10], eax
0x18000741d  movsx   eax, word ptr [rbx+36h]
0x180007421  mov     [rbp+var_C], eax
0x180007424  mov     rcx, r14; hic
0x180007427  lea     r8, [rbp+dw1]; dw1
0x18000742b  mov     r9, rsi; dw2
0x18000742e  mov     edx, edi; msg
0x180007430  call    ICSendMessage
0x180007435  mov     rcx, [rbp+hMem]; hMem
0x180007439  mov     rbx, rax
0x18000743c  call    cs:__imp_LocalFree
0x180007442  mov     rcx, [rbp+var_38]; hMem
0x180007446  test    rcx, rcx
0x180007449  jz      short loc_180007451
0x18000744b  call    cs:__imp_LocalFree
0x180007451  mov     eax, ebx
0x180007453  add     rsp, 70h
0x180007457  pop     r14
0x180007459  pop     rdi
0x18000745a  pop     rsi
0x18000745b  pop     rbx
0x18000745c  pop     rbp
0x18000745d  retn
```
