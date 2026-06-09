# RasPortFree

- ea: `0x18001b660`
- end: `0x18001b7c6`
- name: `RasPortFree`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001b660`
- `0x180021b14`
- `0x180021fd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b6a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b6a9`

## pseudocode

```c
__int64 __fastcall RasPortFree(__int64 a1)
{
  DWORD CurrentProcessId; // eax
  DWORD v3; // esi
  PVOID *v4; // rcx
  unsigned int v5; // edi
  __int64 v6; // rdx
  unsigned int v7; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  CurrentProcessId = GetCurrentProcessId();
  v3 = CurrentProcessId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      106,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v5 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 601);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
      {
        v6 = 108;
LABEL_28:
        WPP_SF_d(v4[2], v6, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
        return v5;
      }
    }
    return v5;
  }
  v7 = SubmitLocalRequest(2u, a1, v3, 0);
  v5 = v7;
  if ( v7 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_24;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v6 = 110;
    goto LABEL_28;
  }
  return v5;
}

```

## disassembly

```asm
0x18001b660  push    rbx
0x18001b662  push    rsi
0x18001b663  push    rdi
0x18001b664  push    r14
0x18001b666  push    r15
0x18001b668  sub     rsp, 20h
0x18001b66c  mov     rdi, rcx
0x18001b66f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b676  lea     r14, WPP_GLOBAL_Control
0x18001b67d  lea     r15, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b684  cmp     rcx, r14
0x18001b687  jz      short loc_18001B6A9
0x18001b689  test    byte ptr [rcx+1Ch], 40h
0x18001b68d  jz      short loc_18001B6A9
0x18001b68f  cmp     byte ptr [rcx+19h], 6
0x18001b693  jb      short loc_18001B6A9
0x18001b695  mov     rcx, [rcx+10h]
0x18001b699  mov     edx, 69h ; 'i'
0x18001b69e  mov     r9, rdi
0x18001b6a1  mov     r8, r15
0x18001b6a4  call    WPP_SF_q
0x18001b6a9  call    cs:__imp_GetCurrentProcessId
0x18001b6b0  nop     dword ptr [rax+rax+00h]
0x18001b6b5  mov     esi, eax
0x18001b6b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6be  cmp     rcx, r14
0x18001b6c1  jz      short loc_18001B6E3
0x18001b6c3  test    byte ptr [rcx+1Ch], 40h
0x18001b6c7  jz      short loc_18001B6E3
0x18001b6c9  cmp     byte ptr [rcx+19h], 5
0x18001b6cd  jb      short loc_18001B6E3
0x18001b6cf  mov     rcx, [rcx+10h]
0x18001b6d3  mov     edx, 6Ah ; 'j'
0x18001b6d8  mov     r9d, eax
0x18001b6db  mov     r8, r15
0x18001b6de  call    WPP_SF_d
0x18001b6e3  mov     rcx, rdi
0x18001b6e6  call    ValidatePortHandle
0x18001b6eb  test    eax, eax
0x18001b6ed  jnz     short loc_18001B747
0x18001b6ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6f6  mov     edi, 259h
0x18001b6fb  cmp     rcx, r14
0x18001b6fe  jz      loc_18001B7B7
0x18001b704  test    byte ptr [rcx+1Ch], 40h
0x18001b708  jz      short loc_18001B72B
0x18001b70a  lea     ebx, [rax+2]
0x18001b70d  cmp     [rcx+19h], bl
0x18001b710  jb      short loc_18001B72B
0x18001b712  mov     rcx, [rcx+10h]
0x18001b716  lea     edx, [rax+6Bh]
0x18001b719  mov     r9d, edi
0x18001b71c  mov     r8, r15
0x18001b71f  call    WPP_SF_d
0x18001b724  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b72b  cmp     rcx, r14
0x18001b72e  jz      loc_18001B7B7
0x18001b734  test    byte ptr [rcx+1Ch], 40h
0x18001b738  jz      short loc_18001B7B7
0x18001b73a  cmp     byte ptr [rcx+19h], 6
0x18001b73e  jb      short loc_18001B7B7
0x18001b740  mov     edx, 6Ch ; 'l'
0x18001b745  jmp     short loc_18001B7A8
0x18001b747  mov     ebx, 2
0x18001b74c  xor     r9d, r9d
0x18001b74f  mov     ecx, ebx
0x18001b751  mov     r8d, esi
0x18001b754  mov     rdx, rdi
0x18001b757  call    SubmitLocalRequest
0x18001b75c  mov     edi, eax
0x18001b75e  test    eax, eax
0x18001b760  jz      short loc_18001B78B
0x18001b762  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b769  cmp     rcx, r14
0x18001b76c  jz      short loc_18001B7B7
0x18001b76e  test    byte ptr [rcx+1Ch], 40h
0x18001b772  jz      short loc_18001B792
0x18001b774  cmp     [rcx+19h], bl
0x18001b777  jb      short loc_18001B792
0x18001b779  mov     rcx, [rcx+10h]
0x18001b77d  lea     edx, [rbx+6Bh]
0x18001b780  mov     r9d, eax
0x18001b783  mov     r8, r15
0x18001b786  call    WPP_SF_d
0x18001b78b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b792  cmp     rcx, r14
0x18001b795  jz      short loc_18001B7B7
0x18001b797  test    byte ptr [rcx+1Ch], 40h
0x18001b79b  jz      short loc_18001B7B7
0x18001b79d  cmp     byte ptr [rcx+19h], 6
0x18001b7a1  jb      short loc_18001B7B7
0x18001b7a3  mov     edx, 6Eh ; 'n'
0x18001b7a8  mov     rcx, [rcx+10h]
0x18001b7ac  mov     r9d, edi
0x18001b7af  mov     r8, r15
0x18001b7b2  call    WPP_SF_d
0x18001b7b7  mov     eax, edi
0x18001b7b9  add     rsp, 20h
0x18001b7bd  pop     r15
0x18001b7bf  pop     r14
0x18001b7c1  pop     rdi
0x18001b7c2  pop     rsi
0x18001b7c3  pop     rbx
0x18001b7c4  retn
```
