# RasDeviceConnect

- ea: `0x180017cb0`
- end: `0x180017e16`
- name: `RasDeviceConnect`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x180017cb0`
- `0x180021b14`
- `0x180021fd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017d44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017d44`

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
0x180017cb0  push    rbx
0x180017cb2  push    rbp
0x180017cb3  push    rsi
0x180017cb4  push    rdi
0x180017cb5  push    r12
0x180017cb7  push    r13
0x180017cb9  push    r14
0x180017cbb  sub     rsp, 40h
0x180017cbf  mov     esi, r9d
0x180017cc2  mov     rbp, r8
0x180017cc5  mov     r14, rdx
0x180017cc8  mov     rbx, rcx
0x180017ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cd2  lea     r12, WPP_GLOBAL_Control
0x180017cd9  lea     r13, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180017ce0  cmp     rcx, r12
0x180017ce3  jz      short loc_180017D05
0x180017ce5  test    byte ptr [rcx+1Ch], 40h
0x180017ce9  jz      short loc_180017D05
0x180017ceb  cmp     byte ptr [rcx+19h], 6
0x180017cef  jb      short loc_180017D05
0x180017cf1  mov     rcx, [rcx+10h]
0x180017cf5  mov     edx, 0DEh
0x180017cfa  mov     r9, rbx
0x180017cfd  mov     r8, r13
0x180017d00  call    WPP_SF_q
0x180017d05  mov     rcx, rbx
0x180017d08  call    ValidatePortHandle
0x180017d0d  test    eax, eax
0x180017d0f  jnz     short loc_180017D44
0x180017d11  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d18  mov     ebx, 259h
0x180017d1d  cmp     rcx, r12
0x180017d20  jz      loc_180017E04
0x180017d26  test    byte ptr [rcx+1Ch], 40h
0x180017d2a  jz      loc_180017E04
0x180017d30  cmp     byte ptr [rcx+19h], 2
0x180017d34  jb      loc_180017E04
0x180017d3a  mov     edx, 0DFh
0x180017d3f  jmp     loc_180017DF5
0x180017d44  call    cs:__imp_GetCurrentProcessId
0x180017d4b  nop     dword ptr [rax+rax+00h]
0x180017d50  mov     edi, eax
0x180017d52  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d59  cmp     rcx, r12
0x180017d5c  jz      short loc_180017D7E
0x180017d5e  test    byte ptr [rcx+1Ch], 40h
0x180017d62  jz      short loc_180017D7E
0x180017d64  cmp     byte ptr [rcx+19h], 5
0x180017d68  jb      short loc_180017D7E
0x180017d6a  mov     rcx, [rcx+10h]
0x180017d6e  mov     edx, 0E0h
0x180017d73  mov     r9d, eax
0x180017d76  mov     r8, r13
0x180017d79  call    WPP_SF_d
0x180017d7e  mov     rax, [rsp+78h+arg_20]
0x180017d86  mov     ecx, 0Fh
0x180017d8b  mov     [rsp+78h+var_48], edi
0x180017d8f  mov     r9, rbp
0x180017d92  mov     [rsp+78h+var_50], rax
0x180017d97  mov     r8, r14
0x180017d9a  mov     rdx, rbx
0x180017d9d  mov     [rsp+78h+var_58], esi
0x180017da1  call    SubmitLocalRequest
0x180017da6  mov     ebx, eax
0x180017da8  test    eax, eax
0x180017daa  jz      short loc_180017DD8
0x180017dac  mov     rcx, cs:WPP_GLOBAL_Control
0x180017db3  cmp     rcx, r12
0x180017db6  jz      short loc_180017E04
0x180017db8  test    byte ptr [rcx+1Ch], 40h
0x180017dbc  jz      short loc_180017DDF
0x180017dbe  cmp     byte ptr [rcx+19h], 2
0x180017dc2  jb      short loc_180017DDF
0x180017dc4  mov     rcx, [rcx+10h]
0x180017dc8  mov     edx, 0E1h
0x180017dcd  mov     r9d, eax
0x180017dd0  mov     r8, r13
0x180017dd3  call    WPP_SF_d
0x180017dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ddf  cmp     rcx, r12
0x180017de2  jz      short loc_180017E04
0x180017de4  test    byte ptr [rcx+1Ch], 40h
0x180017de8  jz      short loc_180017E04
0x180017dea  cmp     byte ptr [rcx+19h], 6
0x180017dee  jb      short loc_180017E04
0x180017df0  mov     edx, 0E2h
0x180017df5  mov     rcx, [rcx+10h]
0x180017df9  mov     r9d, ebx
0x180017dfc  mov     r8, r13
0x180017dff  call    WPP_SF_d
0x180017e04  mov     eax, ebx
0x180017e06  add     rsp, 40h
0x180017e0a  pop     r14
0x180017e0c  pop     r13
0x180017e0e  pop     r12
0x180017e10  pop     rdi
0x180017e11  pop     rsi
0x180017e12  pop     rbp
0x180017e13  pop     rbx
0x180017e14  retn
```
