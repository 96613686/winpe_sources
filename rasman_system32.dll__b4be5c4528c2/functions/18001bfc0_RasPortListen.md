# RasPortListen

- ea: `0x18001bfc0`
- end: `0x18001c153`
- name: `RasPortListen`
- size: `403`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001bfc0`
- `0x180021b14`
- `0x180022534`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c080`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c080`

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
0x18001bfc0  push    rbp
0x18001bfc2  push    rsi
0x18001bfc3  push    rdi
0x18001bfc4  push    r12
0x18001bfc6  push    r14
0x18001bfc8  sub     rsp, 30h
0x18001bfcc  mov     rsi, r8
0x18001bfcf  mov     ebp, edx
0x18001bfd1  mov     rdi, rcx
0x18001bfd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfdb  lea     r12, WPP_GLOBAL_Control
0x18001bfe2  cmp     rcx, r12
0x18001bfe5  jz      short loc_18001C00D
0x18001bfe7  test    byte ptr [rcx+1Ch], 40h
0x18001bfeb  jz      short loc_18001C00D
0x18001bfed  cmp     byte ptr [rcx+19h], 6
0x18001bff1  jb      short loc_18001C00D
0x18001bff3  mov     rcx, [rcx+10h]
0x18001bff7  mov     edx, 0A6h
0x18001bffc  mov     [rsp+58h+var_30], r8
0x18001c001  mov     r9, rdi
0x18001c004  mov     dword ptr [rsp+58h+var_38], ebp
0x18001c008  call    WPP_SF_qdq
0x18001c00d  mov     rcx, rdi
0x18001c010  call    ValidatePortHandle
0x18001c015  test    eax, eax
0x18001c017  jnz     short loc_18001C080
0x18001c019  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c020  mov     edi, 259h
0x18001c025  cmp     rcx, r12
0x18001c028  jz      loc_18001C144
0x18001c02e  test    byte ptr [rcx+1Ch], 40h
0x18001c032  jz      short loc_18001C059
0x18001c034  cmp     byte ptr [rcx+19h], 2
0x18001c038  jb      short loc_18001C059
0x18001c03a  mov     rcx, [rcx+10h]
0x18001c03e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c045  mov     edx, 0A7h
0x18001c04a  mov     r9d, edi
0x18001c04d  call    WPP_SF_d
0x18001c052  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c059  cmp     rcx, r12
0x18001c05c  jz      loc_18001C144
0x18001c062  test    byte ptr [rcx+1Ch], 40h
0x18001c066  jz      loc_18001C144
0x18001c06c  cmp     byte ptr [rcx+19h], 6
0x18001c070  jb      loc_18001C144
0x18001c076  mov     edx, 0A8h
0x18001c07b  jmp     loc_18001C131
0x18001c080  call    cs:__imp_GetCurrentProcessId
0x18001c087  nop     dword ptr [rax+rax+00h]
0x18001c08c  mov     r14d, eax
0x18001c08f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c096  mov     eax, 5
0x18001c09b  cmp     rcx, r12
0x18001c09e  jz      short loc_18001C0C8
0x18001c0a0  test    byte ptr [rcx+1Ch], 40h
0x18001c0a4  jz      short loc_18001C0C8
0x18001c0a6  cmp     [rcx+19h], al
0x18001c0a9  jb      short loc_18001C0C8
0x18001c0ab  mov     rcx, [rcx+10h]
0x18001c0af  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c0b6  mov     edx, 0A9h
0x18001c0bb  mov     r9d, r14d
0x18001c0be  call    WPP_SF_d
0x18001c0c3  mov     eax, 5
0x18001c0c8  mov     r9, rsi
0x18001c0cb  movzx   ecx, ax
0x18001c0ce  mov     r8d, ebp
0x18001c0d1  mov     dword ptr [rsp+58h+var_38], r14d
0x18001c0d6  mov     rdx, rdi
0x18001c0d9  call    SubmitLocalRequest
0x18001c0de  mov     edi, eax
0x18001c0e0  test    eax, eax
0x18001c0e2  jz      short loc_18001C114
0x18001c0e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0eb  cmp     rcx, r12
0x18001c0ee  jz      short loc_18001C144
0x18001c0f0  test    byte ptr [rcx+1Ch], 40h
0x18001c0f4  jz      short loc_18001C11B
0x18001c0f6  cmp     byte ptr [rcx+19h], 2
0x18001c0fa  jb      short loc_18001C11B
0x18001c0fc  mov     rcx, [rcx+10h]
0x18001c100  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c107  mov     edx, 0AAh
0x18001c10c  mov     r9d, eax
0x18001c10f  call    WPP_SF_d
0x18001c114  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c11b  cmp     rcx, r12
0x18001c11e  jz      short loc_18001C144
0x18001c120  test    byte ptr [rcx+1Ch], 40h
0x18001c124  jz      short loc_18001C144
0x18001c126  cmp     byte ptr [rcx+19h], 6
0x18001c12a  jb      short loc_18001C144
0x18001c12c  mov     edx, 0ABh
0x18001c131  mov     rcx, [rcx+10h]
0x18001c135  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c13c  mov     r9d, edi
0x18001c13f  call    WPP_SF_d
0x18001c144  mov     eax, edi
0x18001c146  add     rsp, 30h
0x18001c14a  pop     r14
0x18001c14c  pop     r12
0x18001c14e  pop     rdi
0x18001c14f  pop     rsi
0x18001c150  pop     rbp
0x18001c151  retn
```
