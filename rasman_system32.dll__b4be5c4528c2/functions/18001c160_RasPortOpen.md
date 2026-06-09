# RasPortOpen

- ea: `0x18001c160`
- end: `0x18001c278`
- name: `RasPortOpen`
- size: `280`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1800030d0`
- `0x18001c160`
- `0x180021ae4`
- `0x180021b14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c1a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c1a8`

## pseudocode

```c
__int64 __fastcall RasPortOpen(__int64 a1, __int64 a2, __int64 a3)
{
  DWORD CurrentProcessId; // eax
  DWORD v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  int v12; // [rsp+20h] [rbp-38h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  CurrentProcessId = GetCurrentProcessId();
  v7 = CurrentProcessId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      91,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  v12 = 1;
  v8 = SubmitLocalRequest(1u, a1, a3, v7, v12, a2);
  v9 = v8;
  if ( !v8 )
    goto LABEL_14;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
LABEL_14:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 93, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18001c160  push    rbx
0x18001c162  push    rbp
0x18001c163  push    rsi
0x18001c164  push    rdi
0x18001c165  push    r15
0x18001c167  sub     rsp, 30h
0x18001c16b  mov     rdi, r8
0x18001c16e  mov     rsi, rdx
0x18001c171  mov     rbp, rcx
0x18001c174  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c17b  lea     r15, WPP_GLOBAL_Control
0x18001c182  cmp     rcx, r15
0x18001c185  jz      short loc_18001C1A8
0x18001c187  test    byte ptr [rcx+1Ch], 40h
0x18001c18b  jz      short loc_18001C1A8
0x18001c18d  cmp     byte ptr [rcx+19h], 6
0x18001c191  jb      short loc_18001C1A8
0x18001c193  mov     rcx, [rcx+10h]
0x18001c197  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c19e  mov     edx, 5Ah ; 'Z'
0x18001c1a3  call    WPP_SF_
0x18001c1a8  call    cs:__imp_GetCurrentProcessId
0x18001c1af  nop     dword ptr [rax+rax+00h]
0x18001c1b4  mov     ebx, eax
0x18001c1b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1bd  cmp     rcx, r15
0x18001c1c0  jz      short loc_18001C1E6
0x18001c1c2  test    byte ptr [rcx+1Ch], 40h
0x18001c1c6  jz      short loc_18001C1E6
0x18001c1c8  cmp     byte ptr [rcx+19h], 5
0x18001c1cc  jb      short loc_18001C1E6
0x18001c1ce  mov     rcx, [rcx+10h]
0x18001c1d2  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c1d9  mov     edx, 5Bh ; '['
0x18001c1de  mov     r9d, eax
0x18001c1e1  call    WPP_SF_d
0x18001c1e6  mov     eax, 1
0x18001c1eb  mov     [rsp+58h+var_30], rsi
0x18001c1f0  mov     ecx, eax
0x18001c1f2  mov     [rsp+58h+var_38], eax
0x18001c1f6  mov     r9d, ebx
0x18001c1f9  mov     r8, rdi
0x18001c1fc  mov     rdx, rbp
0x18001c1ff  call    SubmitLocalRequest
0x18001c204  mov     ebx, eax
0x18001c206  test    eax, eax
0x18001c208  jz      short loc_18001C23A
0x18001c20a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c211  cmp     rcx, r15
0x18001c214  jz      short loc_18001C26A
0x18001c216  test    byte ptr [rcx+1Ch], 40h
0x18001c21a  jz      short loc_18001C241
0x18001c21c  cmp     byte ptr [rcx+19h], 2
0x18001c220  jb      short loc_18001C241
0x18001c222  mov     rcx, [rcx+10h]
0x18001c226  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c22d  mov     edx, 5Ch ; '\'
0x18001c232  mov     r9d, eax
0x18001c235  call    WPP_SF_d
0x18001c23a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c241  cmp     rcx, r15
0x18001c244  jz      short loc_18001C26A
0x18001c246  test    byte ptr [rcx+1Ch], 40h
0x18001c24a  jz      short loc_18001C26A
0x18001c24c  cmp     byte ptr [rcx+19h], 6
0x18001c250  jb      short loc_18001C26A
0x18001c252  mov     rcx, [rcx+10h]
0x18001c256  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c25d  mov     edx, 5Dh ; ']'
0x18001c262  mov     r9d, ebx
0x18001c265  call    WPP_SF_d
0x18001c26a  mov     eax, ebx
0x18001c26c  add     rsp, 30h
0x18001c270  pop     r15
0x18001c272  pop     rdi
0x18001c273  pop     rsi
0x18001c274  pop     rbp
0x18001c275  pop     rbx
0x18001c276  retn
```
