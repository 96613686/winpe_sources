# RasDeviceConnect

- ea: `0x1800172f0`
- end: `0x18001744f`
- name: `RasDeviceConnect`
- size: `351`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x1800172f0`
- `0x180021000`
- `0x180021488`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017384`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017384`

## pseudocode

```c
__int64 __fastcall RasDeviceConnect(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  PVOID *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  DWORD CurrentProcessId; // eax
  DWORD v13; // edi
  unsigned int v14; // eax
  int v16; // [rsp+20h] [rbp-58h]
  DWORD v17; // [rsp+30h] [rbp-48h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v10 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 223;
LABEL_24:
      WPP_SF_d(v9[2], v11, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
      return v10;
    }
    return v10;
  }
  CurrentProcessId = GetCurrentProcessId();
  v13 = CurrentProcessId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      224,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  v17 = v13;
  v16 = a4;
  v14 = SubmitLocalRequest(0xFu, a1, a2, a3, v16, a5, v17);
  v10 = v14;
  if ( v14 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v10;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_20;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 225, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v14);
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 6u )
  {
    v11 = 226;
    goto LABEL_24;
  }
  return v10;
}

```

## disassembly

```asm
0x1800172f0  push    rbx
0x1800172f2  push    rbp
0x1800172f3  push    rsi
0x1800172f4  push    rdi
0x1800172f5  push    r12
0x1800172f7  push    r13
0x1800172f9  push    r14
0x1800172fb  sub     rsp, 40h
0x1800172ff  mov     esi, r9d
0x180017302  mov     rbp, r8
0x180017305  mov     r14, rdx
0x180017308  mov     rbx, rcx
0x18001730b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017312  lea     r12, WPP_GLOBAL_Control
0x180017319  lea     r13, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180017320  cmp     rcx, r12
0x180017323  jz      short loc_180017345
0x180017325  test    byte ptr [rcx+1Ch], 40h
0x180017329  jz      short loc_180017345
0x18001732b  cmp     byte ptr [rcx+19h], 6
0x18001732f  jb      short loc_180017345
0x180017331  mov     rcx, [rcx+10h]
0x180017335  mov     edx, 0DEh
0x18001733a  mov     r9, rbx
0x18001733d  mov     r8, r13
0x180017340  call    WPP_SF_q
0x180017345  mov     rcx, rbx
0x180017348  call    ValidatePortHandle
0x18001734d  test    eax, eax
0x18001734f  jnz     short loc_180017384
0x180017351  mov     rcx, cs:WPP_GLOBAL_Control
0x180017358  mov     ebx, 259h
0x18001735d  cmp     rcx, r12
0x180017360  jz      loc_18001743E
0x180017366  test    byte ptr [rcx+1Ch], 40h
0x18001736a  jz      loc_18001743E
0x180017370  cmp     byte ptr [rcx+19h], 2
0x180017374  jb      loc_18001743E
0x18001737a  mov     edx, 0DFh
0x18001737f  jmp     loc_18001742F
0x180017384  call    cs:__imp_GetCurrentProcessId
0x18001738a  mov     edi, eax
0x18001738c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017393  cmp     rcx, r12
0x180017396  jz      short loc_1800173B8
0x180017398  test    byte ptr [rcx+1Ch], 40h
0x18001739c  jz      short loc_1800173B8
0x18001739e  cmp     byte ptr [rcx+19h], 5
0x1800173a2  jb      short loc_1800173B8
0x1800173a4  mov     rcx, [rcx+10h]
0x1800173a8  mov     edx, 0E0h
0x1800173ad  mov     r9d, eax
0x1800173b0  mov     r8, r13
0x1800173b3  call    WPP_SF_d
0x1800173b8  mov     rax, [rsp+78h+arg_20]
0x1800173c0  mov     ecx, 0Fh
0x1800173c5  mov     [rsp+78h+var_48], edi
0x1800173c9  mov     r9, rbp
0x1800173cc  mov     [rsp+78h+var_50], rax
0x1800173d1  mov     r8, r14
0x1800173d4  mov     rdx, rbx
0x1800173d7  mov     [rsp+78h+var_58], esi
0x1800173db  call    SubmitLocalRequest
0x1800173e0  mov     ebx, eax
0x1800173e2  test    eax, eax
0x1800173e4  jz      short loc_180017412
0x1800173e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173ed  cmp     rcx, r12
0x1800173f0  jz      short loc_18001743E
0x1800173f2  test    byte ptr [rcx+1Ch], 40h
0x1800173f6  jz      short loc_180017419
0x1800173f8  cmp     byte ptr [rcx+19h], 2
0x1800173fc  jb      short loc_180017419
0x1800173fe  mov     rcx, [rcx+10h]
0x180017402  mov     edx, 0E1h
0x180017407  mov     r9d, eax
0x18001740a  mov     r8, r13
0x18001740d  call    WPP_SF_d
0x180017412  mov     rcx, cs:WPP_GLOBAL_Control
0x180017419  cmp     rcx, r12
0x18001741c  jz      short loc_18001743E
0x18001741e  test    byte ptr [rcx+1Ch], 40h
0x180017422  jz      short loc_18001743E
0x180017424  cmp     byte ptr [rcx+19h], 6
0x180017428  jb      short loc_18001743E
0x18001742a  mov     edx, 0E2h
0x18001742f  mov     rcx, [rcx+10h]
0x180017433  mov     r9d, ebx
0x180017436  mov     r8, r13
0x180017439  call    WPP_SF_d
0x18001743e  mov     eax, ebx
0x180017440  add     rsp, 40h
0x180017444  pop     r14
0x180017446  pop     r13
0x180017448  pop     r12
0x18001744a  pop     rdi
0x18001744b  pop     rsi
0x18001744c  pop     rbp
0x18001744d  pop     rbx
0x18001744e  retn
```
