# _drr_ErodeTombStones

- ea: `0x1800045f4`
- end: `0x1800047cb`
- name: `_drr_ErodeTombStones`
- size: `471`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180006230`

## callees

- `0x1800045f4`
- `0x180004a2c`
- `0x18000702c`
- `0x18000d34c`
- `0x18000d8d0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800046cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800046cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047a5`
- `ntdll!EtwEventWrite` at `0x18000479c`
- `ntdll!EtwEventWrite` at `0x18000479c`

## pseudocode

```c
__int64 __fastcall drr_ErodeTombStones(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // edi
  __int64 v7; // r11
  __int64 v8; // r11
  DWORD v9; // ecx
  __int64 v10; // rcx
  __int64 v11; // r8
  int v13; // eax
  HLOCAL v14; // rbx
  __int64 v15; // rax
  int v16; // eax
  DWORD v18; // [rsp+20h] [rbp-40h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-38h]
  _QWORD v20[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 *v21; // [rsp+40h] [rbp-20h]
  int v22; // [rsp+48h] [rbp-18h]
  int v23; // [rsp+4Ch] [rbp-14h]

  v6 = 0;
  v18 = 0;
  while ( v6 < *(_DWORD *)(a2 + 120) )
  {
    v7 = *(_QWORD *)(*(_QWORD *)(a2 + 112) + 8LL * v6);
    if ( (*(_BYTE *)(v7 + 104) & 1) != 0 && (unsigned int)drr_IsTombStoneEroded(v7 + 96, a3) )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 32LL))(a1, v8);
      if ( (v9 & 0x1FFF0000) == 0x70000 )
        v9 = (unsigned __int16)v9;
      v18 = v9;
      if ( v9 )
        return v9;
      DRR_SecureFreeRoamingToken(*(_QWORD *)(*(_QWORD *)(a2 + 112) + 8LL * v6));
      v10 = v6;
      if ( v6 < *(_DWORD *)(a2 + 120) - 1 )
      {
        do
        {
          v11 = (unsigned int)(v10 + 1);
          *(_QWORD *)(*(_QWORD *)(a2 + 112) + 8 * v10) = *(_QWORD *)(*(_QWORD *)(a2 + 112) + 8 * v11);
          v10 = v11;
        }
        while ( (unsigned int)v11 < *(_DWORD *)(a2 + 120) - 1 );
      }
      *(_QWORD *)(*(_QWORD *)(a2 + 112) + 8 * v10) = 0;
      if ( (*(_DWORD *)(a2 + 120))-- == 1 )
      {
        LocalFree(*(HLOCAL *)(a2 + 112));
        *(_QWORD *)(a2 + 112) = 0;
        *(_DWORD *)(a2 + 124) = 0;
      }
    }
    else
    {
      ++v6;
    }
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 80LL))(a1, a3);
  if ( (v9 & 0x1FFF0000) == 0x70000 )
    v9 = (unsigned __int16)v9;
  v18 = v9;
  if ( v9 && (unsigned int)g_dwLoglevel > 1 )
  {
    hMem = 0;
    v20[0] = &v18;
    v20[1] = 4;
    v13 = LogErrorCodeAndText(v9);
    v14 = hMem;
    if ( v13 && hMem )
    {
      v15 = -1;
      do
        ++v15;
      while ( *((_WORD *)hMem + v15) );
      v21 = (__int64 *)hMem;
      v16 = 2 * v15 + 2;
    }
    else
    {
      v21 = &qword_18000FCA0;
      v16 = 2;
    }
    v22 = v16;
    v23 = 0;
    if ( qword_1800138C8 )
      EtwEventWrite(qword_1800138C8, DRR_LOG_ERROR_NETSTOREWRITE, 2, v20);
    LocalFree(v14);
    return v18;
  }
  return v9;
}

```

## disassembly

```asm
0x1800045f4  push    rbp
0x1800045f6  push    rbx
0x1800045f7  push    rsi
0x1800045f8  push    rdi
0x1800045f9  push    r12
0x1800045fb  push    r14
0x1800045fd  push    r15
0x1800045ff  mov     rbp, rsp
0x180004602  sub     rsp, 60h
0x180004606  mov     rax, cs:__security_cookie
0x18000460d  xor     rax, rsp
0x180004610  mov     [rbp+var_10], rax
0x180004614  xor     r12d, r12d
0x180004617  mov     r15, r8
0x18000461a  mov     rbx, rdx
0x18000461d  mov     r14, rcx
0x180004620  mov     edi, r12d
0x180004623  mov     [rbp+var_40], r12d
0x180004627  cmp     [rdx+78h], r12d
0x18000462b  jbe     loc_1800046EA
0x180004631  mov     rax, [rbx+70h]
0x180004635  mov     esi, edi
0x180004637  mov     r11, [rax+rsi*8]
0x18000463b  test    byte ptr [r11+68h], 1
0x180004640  jz      loc_1800046DF
0x180004646  lea     rcx, [r11+60h]
0x18000464a  mov     rdx, r15
0x18000464d  call    _drr_IsTombStoneEroded
0x180004652  test    eax, eax
0x180004654  jz      loc_1800046DF
0x18000465a  mov     rax, [r14]
0x18000465d  mov     rdx, r11
0x180004660  mov     rcx, r14
0x180004663  mov     rax, [rax+20h]
0x180004667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000466c  mov     ecx, eax
0x18000466e  and     eax, 1FFF0000h
0x180004673  cmp     eax, 70000h
0x180004678  jnz     short loc_18000467D
0x18000467a  movzx   ecx, cx
0x18000467d  mov     [rbp+var_40], ecx
0x180004680  test    ecx, ecx
0x180004682  jnz     loc_1800047AE
0x180004688  mov     rcx, [rbx+70h]
0x18000468c  mov     rcx, [rcx+rsi*8]
0x180004690  call    DRR_SecureFreeRoamingToken
0x180004695  mov     eax, [rbx+78h]
0x180004698  dec     eax
0x18000469a  mov     ecx, edi
0x18000469c  cmp     edi, eax
0x18000469e  jnb     short loc_1800046BD
0x1800046a0  mov     rdx, [rbx+70h]
0x1800046a4  lea     r8d, [rcx+1]
0x1800046a8  mov     rax, [rdx+r8*8]
0x1800046ac  mov     [rdx+rcx*8], rax
0x1800046b0  mov     eax, [rbx+78h]
0x1800046b3  dec     eax
0x1800046b5  mov     ecx, r8d
0x1800046b8  cmp     r8d, eax
0x1800046bb  jb      short loc_1800046A0
0x1800046bd  mov     rax, [rbx+70h]
0x1800046c1  mov     [rax+rcx*8], r12
0x1800046c5  add     dword ptr [rbx+78h], 0FFFFFFFFh
0x1800046c9  jnz     short loc_1800046E1
0x1800046cb  mov     rcx, [rbx+70h]; hMem
0x1800046cf  call    cs:__imp_LocalFree
0x1800046d5  mov     [rbx+70h], r12
0x1800046d9  mov     [rbx+7Ch], r12d
0x1800046dd  jmp     short loc_1800046E1
0x1800046df  inc     edi
0x1800046e1  cmp     edi, [rbx+78h]
0x1800046e4  jb      loc_180004631
0x1800046ea  mov     rax, [r14]
0x1800046ed  mov     rdx, r15
0x1800046f0  mov     rcx, r14
0x1800046f3  mov     rax, [rax+50h]
0x1800046f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046fc  mov     ecx, eax
0x1800046fe  and     eax, 1FFF0000h
0x180004703  cmp     eax, 70000h
0x180004708  jnz     short loc_18000470D
0x18000470a  movzx   ecx, cx; dwMessageId
0x18000470d  mov     [rbp+var_40], ecx
0x180004710  test    ecx, ecx
0x180004712  jz      loc_1800047AE
0x180004718  cmp     cs:g_dwLoglevel, 1
0x18000471f  jbe     loc_1800047AE
0x180004725  lea     rax, [rbp+var_40]
0x180004729  mov     [rbp+hMem], r12
0x18000472d  lea     rdx, [rbp+hMem]
0x180004731  mov     [rbp+var_30], rax
0x180004735  mov     [rbp+var_28], 4
0x18000473d  call    _LogErrorCodeAndText
0x180004742  mov     rbx, [rbp+hMem]
0x180004746  mov     r8d, 2
0x18000474c  test    eax, eax
0x18000474e  jz      short loc_180004770
0x180004750  test    rbx, rbx
0x180004753  jz      short loc_180004770
0x180004755  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004759  inc     rax
0x18000475c  cmp     [rbx+rax*2], r12w
0x180004761  jnz     short loc_180004759
0x180004763  mov     [rbp+var_20], rbx
0x180004767  lea     eax, ds:2[rax*2]
0x18000476e  jmp     short loc_18000477E
0x180004770  lea     rax, qword_18000FCA0
0x180004777  mov     [rbp+var_20], rax
0x18000477b  mov     eax, r8d
0x18000477e  mov     rcx, cs:qword_1800138C8
0x180004785  mov     [rbp+var_18], eax
0x180004788  mov     [rbp+var_14], r12d
0x18000478c  test    rcx, rcx
0x18000478f  jz      short loc_1800047A2
0x180004791  lea     r9, [rbp+var_30]
0x180004795  lea     rdx, DRR_LOG_ERROR_NETSTOREWRITE
0x18000479c  call    cs:__imp_EtwEventWrite
0x1800047a2  mov     rcx, rbx; hMem
0x1800047a5  call    cs:__imp_LocalFree
0x1800047ab  mov     ecx, [rbp+var_40]
0x1800047ae  mov     eax, ecx
0x1800047b0  mov     rcx, [rbp+var_10]
0x1800047b4  xor     rcx, rsp; StackCookie
0x1800047b7  call    __security_check_cookie
0x1800047bc  add     rsp, 60h
0x1800047c0  pop     r15
0x1800047c2  pop     r14
0x1800047c4  pop     r12
0x1800047c6  pop     rdi
0x1800047c7  pop     rsi
0x1800047c8  pop     rbx
0x1800047c9  pop     rbp
0x1800047ca  retn
```
