# RasPortReceive

- ea: `0x18001c4a0`
- end: `0x18001c65c`
- name: `RasPortReceive`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001eb40`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001c4a0`
- `0x180021b14`
- `0x180022534`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c56f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c56f`

## pseudocode

```c
__int64 __fastcall RasPortReceive(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  PVOID *v9; // rcx
  unsigned int v10; // edi
  __int64 v11; // rdx
  DWORD CurrentProcessId; // esi
  unsigned int v13; // eax
  __int64 v15; // [rsp+20h] [rbp-58h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, a3, a1, a4, a5);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v10 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 601);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 6u )
      {
        v11 = 152;
LABEL_28:
        WPP_SF_d(v9[2], v11, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
        return v10;
      }
    }
    return v10;
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      153,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  LODWORD(v15) = a4;
  v13 = SubmitLocalRequest(7u, a1, a2 - 32, a3, v15, a5, CurrentProcessId);
  v10 = v13;
  if ( v13 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v10;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_24;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v13);
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 6u )
  {
    v11 = 155;
    goto LABEL_28;
  }
  return v10;
}

```

## disassembly

```asm
0x18001c4a0  push    rbp
0x18001c4a2  push    rsi
0x18001c4a3  push    rdi
0x18001c4a4  push    r13
0x18001c4a6  push    r14
0x18001c4a8  push    r15
0x18001c4aa  sub     rsp, 48h
0x18001c4ae  mov     ebp, r9d
0x18001c4b1  mov     r15, r8
0x18001c4b4  mov     r13, rdx
0x18001c4b7  mov     rdi, rcx
0x18001c4ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4c1  lea     rsi, WPP_GLOBAL_Control
0x18001c4c8  mov     r14, [rsp+78h+arg_20]
0x18001c4d0  cmp     rcx, rsi
0x18001c4d3  jz      short loc_18001C4FC
0x18001c4d5  test    byte ptr [rcx+1Ch], 40h
0x18001c4d9  jz      short loc_18001C4FC
0x18001c4db  cmp     byte ptr [rcx+19h], 6
0x18001c4df  jb      short loc_18001C4FC
0x18001c4e1  mov     rcx, [rcx+10h]
0x18001c4e5  mov     edx, 96h
0x18001c4ea  mov     [rsp+78h+var_50], r14
0x18001c4ef  mov     dword ptr [rsp+78h+var_58], r9d
0x18001c4f4  mov     r9, rdi
0x18001c4f7  call    WPP_SF_qdq
0x18001c4fc  mov     rcx, rdi
0x18001c4ff  call    ValidatePortHandle
0x18001c504  test    eax, eax
0x18001c506  jnz     short loc_18001C56F
0x18001c508  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c50f  mov     edi, 259h
0x18001c514  cmp     rcx, rsi
0x18001c517  jz      loc_18001C64B
0x18001c51d  test    byte ptr [rcx+1Ch], 40h
0x18001c521  jz      short loc_18001C548
0x18001c523  cmp     byte ptr [rcx+19h], 2
0x18001c527  jb      short loc_18001C548
0x18001c529  mov     rcx, [rcx+10h]
0x18001c52d  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c534  mov     edx, 97h
0x18001c539  mov     r9d, edi
0x18001c53c  call    WPP_SF_d
0x18001c541  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c548  cmp     rcx, rsi
0x18001c54b  jz      loc_18001C64B
0x18001c551  test    byte ptr [rcx+1Ch], 40h
0x18001c555  jz      loc_18001C64B
0x18001c55b  cmp     byte ptr [rcx+19h], 6
0x18001c55f  jb      loc_18001C64B
0x18001c565  mov     edx, 98h
0x18001c56a  jmp     loc_18001C638
0x18001c56f  call    cs:__imp_GetCurrentProcessId
0x18001c576  nop     dword ptr [rax+rax+00h]
0x18001c57b  mov     esi, eax
0x18001c57d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c584  lea     rax, WPP_GLOBAL_Control
0x18001c58b  cmp     rcx, rax
0x18001c58e  jz      short loc_18001C5B4
0x18001c590  test    byte ptr [rcx+1Ch], 40h
0x18001c594  jz      short loc_18001C5B4
0x18001c596  cmp     byte ptr [rcx+19h], 5
0x18001c59a  jb      short loc_18001C5B4
0x18001c59c  mov     rcx, [rcx+10h]
0x18001c5a0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c5a7  mov     edx, 99h
0x18001c5ac  mov     r9d, esi
0x18001c5af  call    WPP_SF_d
0x18001c5b4  mov     [rsp+78h+var_48], esi
0x18001c5b8  lea     r8, [r13-20h]
0x18001c5bc  mov     [rsp+78h+var_50], r14
0x18001c5c1  mov     ecx, 7
0x18001c5c6  mov     r9, r15
0x18001c5c9  mov     dword ptr [rsp+78h+var_58], ebp
0x18001c5cd  mov     rdx, rdi
0x18001c5d0  call    SubmitLocalRequest
0x18001c5d5  mov     edi, eax
0x18001c5d7  test    eax, eax
0x18001c5d9  jz      short loc_18001C614
0x18001c5db  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5e2  lea     rsi, WPP_GLOBAL_Control
0x18001c5e9  cmp     rcx, rsi
0x18001c5ec  jz      short loc_18001C64B
0x18001c5ee  test    byte ptr [rcx+1Ch], 40h
0x18001c5f2  jz      short loc_18001C622
0x18001c5f4  cmp     byte ptr [rcx+19h], 2
0x18001c5f8  jb      short loc_18001C622
0x18001c5fa  mov     rcx, [rcx+10h]
0x18001c5fe  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c605  mov     edx, 9Ah
0x18001c60a  mov     r9d, eax
0x18001c60d  call    WPP_SF_d
0x18001c612  jmp     short loc_18001C61B
0x18001c614  lea     rsi, WPP_GLOBAL_Control
0x18001c61b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c622  cmp     rcx, rsi
0x18001c625  jz      short loc_18001C64B
0x18001c627  test    byte ptr [rcx+1Ch], 40h
0x18001c62b  jz      short loc_18001C64B
0x18001c62d  cmp     byte ptr [rcx+19h], 6
0x18001c631  jb      short loc_18001C64B
0x18001c633  mov     edx, 9Bh
0x18001c638  mov     rcx, [rcx+10h]
0x18001c63c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c643  mov     r9d, edi
0x18001c646  call    WPP_SF_d
0x18001c64b  mov     eax, edi
0x18001c64d  add     rsp, 48h
0x18001c651  pop     r15
0x18001c653  pop     r14
0x18001c655  pop     r13
0x18001c657  pop     rdi
0x18001c658  pop     rsi
0x18001c659  pop     rbp
0x18001c65a  retn
```
