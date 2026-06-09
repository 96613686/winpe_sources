# RasPortListen

- ea: `0x18001b5a0`
- end: `0x18001b72c`
- name: `RasPortListen`
- size: `396`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001b5a0`
- `0x180021000`
- `0x180021990`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b660`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b660`

## pseudocode

```c
__int64 __fastcall RasPortListen(__int64 a1, unsigned int a2, __int64 a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // edi
  __int64 v8; // rdx
  DWORD CurrentProcessId; // r14d
  unsigned int v10; // eax
  __int64 v12; // [rsp+20h] [rbp-38h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, a3, a1, a2, a3);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v7 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 601);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 6u )
      {
        v8 = 168;
LABEL_28:
        WPP_SF_d(v6[2], v8, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
        return v7;
      }
    }
    return v7;
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      169,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  LODWORD(v12) = CurrentProcessId;
  v10 = SubmitLocalRequest(5u, a1, a2, a3, v12);
  v7 = v10;
  if ( v10 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_24;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 6u )
  {
    v8 = 171;
    goto LABEL_28;
  }
  return v7;
}

```

## disassembly

```asm
0x18001b5a0  push    rbp
0x18001b5a2  push    rsi
0x18001b5a3  push    rdi
0x18001b5a4  push    r12
0x18001b5a6  push    r14
0x18001b5a8  sub     rsp, 30h
0x18001b5ac  mov     rsi, r8
0x18001b5af  mov     ebp, edx
0x18001b5b1  mov     rdi, rcx
0x18001b5b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5bb  lea     r12, WPP_GLOBAL_Control
0x18001b5c2  cmp     rcx, r12
0x18001b5c5  jz      short loc_18001B5ED
0x18001b5c7  test    byte ptr [rcx+1Ch], 40h
0x18001b5cb  jz      short loc_18001B5ED
0x18001b5cd  cmp     byte ptr [rcx+19h], 6
0x18001b5d1  jb      short loc_18001B5ED
0x18001b5d3  mov     rcx, [rcx+10h]
0x18001b5d7  mov     edx, 0A6h
0x18001b5dc  mov     [rsp+58h+var_30], r8
0x18001b5e1  mov     r9, rdi
0x18001b5e4  mov     dword ptr [rsp+58h+var_38], ebp
0x18001b5e8  call    WPP_SF_qdq
0x18001b5ed  mov     rcx, rdi
0x18001b5f0  call    ValidatePortHandle
0x18001b5f5  test    eax, eax
0x18001b5f7  jnz     short loc_18001B660
0x18001b5f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b600  mov     edi, 259h
0x18001b605  cmp     rcx, r12
0x18001b608  jz      loc_18001B71E
0x18001b60e  test    byte ptr [rcx+1Ch], 40h
0x18001b612  jz      short loc_18001B639
0x18001b614  cmp     byte ptr [rcx+19h], 2
0x18001b618  jb      short loc_18001B639
0x18001b61a  mov     rcx, [rcx+10h]
0x18001b61e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b625  mov     edx, 0A7h
0x18001b62a  mov     r9d, edi
0x18001b62d  call    WPP_SF_d
0x18001b632  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b639  cmp     rcx, r12
0x18001b63c  jz      loc_18001B71E
0x18001b642  test    byte ptr [rcx+1Ch], 40h
0x18001b646  jz      loc_18001B71E
0x18001b64c  cmp     byte ptr [rcx+19h], 6
0x18001b650  jb      loc_18001B71E
0x18001b656  mov     edx, 0A8h
0x18001b65b  jmp     loc_18001B70B
0x18001b660  call    cs:__imp_GetCurrentProcessId
0x18001b666  mov     r14d, eax
0x18001b669  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b670  mov     eax, 5
0x18001b675  cmp     rcx, r12
0x18001b678  jz      short loc_18001B6A2
0x18001b67a  test    byte ptr [rcx+1Ch], 40h
0x18001b67e  jz      short loc_18001B6A2
0x18001b680  cmp     [rcx+19h], al
0x18001b683  jb      short loc_18001B6A2
0x18001b685  mov     rcx, [rcx+10h]
0x18001b689  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b690  mov     edx, 0A9h
0x18001b695  mov     r9d, r14d
0x18001b698  call    WPP_SF_d
0x18001b69d  mov     eax, 5
0x18001b6a2  mov     r9, rsi
0x18001b6a5  movzx   ecx, ax
0x18001b6a8  mov     r8d, ebp
0x18001b6ab  mov     dword ptr [rsp+58h+var_38], r14d
0x18001b6b0  mov     rdx, rdi
0x18001b6b3  call    SubmitLocalRequest
0x18001b6b8  mov     edi, eax
0x18001b6ba  test    eax, eax
0x18001b6bc  jz      short loc_18001B6EE
0x18001b6be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6c5  cmp     rcx, r12
0x18001b6c8  jz      short loc_18001B71E
0x18001b6ca  test    byte ptr [rcx+1Ch], 40h
0x18001b6ce  jz      short loc_18001B6F5
0x18001b6d0  cmp     byte ptr [rcx+19h], 2
0x18001b6d4  jb      short loc_18001B6F5
0x18001b6d6  mov     rcx, [rcx+10h]
0x18001b6da  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b6e1  mov     edx, 0AAh
0x18001b6e6  mov     r9d, eax
0x18001b6e9  call    WPP_SF_d
0x18001b6ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6f5  cmp     rcx, r12
0x18001b6f8  jz      short loc_18001B71E
0x18001b6fa  test    byte ptr [rcx+1Ch], 40h
0x18001b6fe  jz      short loc_18001B71E
0x18001b700  cmp     byte ptr [rcx+19h], 6
0x18001b704  jb      short loc_18001B71E
0x18001b706  mov     edx, 0ABh
0x18001b70b  mov     rcx, [rcx+10h]
0x18001b70f  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b716  mov     r9d, edi
0x18001b719  call    WPP_SF_d
0x18001b71e  mov     eax, edi
0x18001b720  add     rsp, 30h
0x18001b724  pop     r14
0x18001b726  pop     r12
0x18001b728  pop     rdi
0x18001b729  pop     rsi
0x18001b72a  pop     rbp
0x18001b72b  retn
```
