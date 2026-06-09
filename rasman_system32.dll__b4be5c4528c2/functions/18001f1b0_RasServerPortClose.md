# RasServerPortClose

- ea: `0x18001f1b0`
- end: `0x18001f312`
- name: `RasServerPortClose`
- size: `354`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001f1b0`
- `0x180021b14`
- `0x180021fd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f1f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f1f7`

## pseudocode

```c
__int64 __fastcall RasServerPortClose(__int64 a1)
{
  DWORD CurrentProcessId; // eax
  DWORD v3; // edi
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 502, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  CurrentProcessId = GetCurrentProcessId();
  v3 = CurrentProcessId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      503,
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 504, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 601);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
      {
        v6 = 505;
LABEL_28:
        WPP_SF_d(v4[2], v6, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
        return v5;
      }
    }
    return v5;
  }
  v7 = SubmitLocalRequest(0x51u, a1, v3, 1);
  v5 = v7;
  if ( v7 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_24;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 506, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v6 = 507;
    goto LABEL_28;
  }
  return v5;
}

```

## disassembly

```asm
0x18001f1b0  push    rbx
0x18001f1b2  push    rbp
0x18001f1b3  push    rdi
0x18001f1b4  push    r14
0x18001f1b6  sub     rsp, 28h
0x18001f1ba  mov     rbx, rcx
0x18001f1bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1c4  lea     rbp, WPP_GLOBAL_Control
0x18001f1cb  lea     r14, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001f1d2  cmp     rcx, rbp
0x18001f1d5  jz      short loc_18001F1F7
0x18001f1d7  test    byte ptr [rcx+1Ch], 40h
0x18001f1db  jz      short loc_18001F1F7
0x18001f1dd  cmp     byte ptr [rcx+19h], 6
0x18001f1e1  jb      short loc_18001F1F7
0x18001f1e3  mov     rcx, [rcx+10h]
0x18001f1e7  mov     edx, 1F6h
0x18001f1ec  mov     r9, rbx
0x18001f1ef  mov     r8, r14
0x18001f1f2  call    WPP_SF_q
0x18001f1f7  call    cs:__imp_GetCurrentProcessId
0x18001f1fe  nop     dword ptr [rax+rax+00h]
0x18001f203  mov     edi, eax
0x18001f205  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f20c  cmp     rcx, rbp
0x18001f20f  jz      short loc_18001F231
0x18001f211  test    byte ptr [rcx+1Ch], 40h
0x18001f215  jz      short loc_18001F231
0x18001f217  cmp     byte ptr [rcx+19h], 5
0x18001f21b  jb      short loc_18001F231
0x18001f21d  mov     rcx, [rcx+10h]
0x18001f221  mov     edx, 1F7h
0x18001f226  mov     r9d, eax
0x18001f229  mov     r8, r14
0x18001f22c  call    WPP_SF_d
0x18001f231  mov     rcx, rbx
0x18001f234  call    ValidatePortHandle
0x18001f239  test    eax, eax
0x18001f23b  jnz     short loc_18001F293
0x18001f23d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f244  mov     ebx, 259h
0x18001f249  cmp     rcx, rbp
0x18001f24c  jz      loc_18001F305
0x18001f252  test    byte ptr [rcx+1Ch], 40h
0x18001f256  jz      short loc_18001F277
0x18001f258  cmp     byte ptr [rcx+19h], 2
0x18001f25c  jb      short loc_18001F277
0x18001f25e  mov     rcx, [rcx+10h]
0x18001f262  lea     edx, [rbx-61h]
0x18001f265  mov     r9d, ebx
0x18001f268  mov     r8, r14
0x18001f26b  call    WPP_SF_d
0x18001f270  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f277  cmp     rcx, rbp
0x18001f27a  jz      loc_18001F305
0x18001f280  test    byte ptr [rcx+1Ch], 40h
0x18001f284  jz      short loc_18001F305
0x18001f286  cmp     byte ptr [rcx+19h], 6
0x18001f28a  jb      short loc_18001F305
0x18001f28c  mov     edx, 1F9h
0x18001f291  jmp     short loc_18001F2F6
0x18001f293  mov     ecx, 51h ; 'Q'
0x18001f298  mov     r8d, edi
0x18001f29b  mov     rdx, rbx
0x18001f29e  lea     r9d, [rcx-50h]
0x18001f2a2  call    SubmitLocalRequest
0x18001f2a7  mov     ebx, eax
0x18001f2a9  test    eax, eax
0x18001f2ab  jz      short loc_18001F2D9
0x18001f2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2b4  cmp     rcx, rbp
0x18001f2b7  jz      short loc_18001F305
0x18001f2b9  test    byte ptr [rcx+1Ch], 40h
0x18001f2bd  jz      short loc_18001F2E0
0x18001f2bf  cmp     byte ptr [rcx+19h], 2
0x18001f2c3  jb      short loc_18001F2E0
0x18001f2c5  mov     rcx, [rcx+10h]
0x18001f2c9  mov     edx, 1FAh
0x18001f2ce  mov     r9d, eax
0x18001f2d1  mov     r8, r14
0x18001f2d4  call    WPP_SF_d
0x18001f2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2e0  cmp     rcx, rbp
0x18001f2e3  jz      short loc_18001F305
0x18001f2e5  test    byte ptr [rcx+1Ch], 40h
0x18001f2e9  jz      short loc_18001F305
0x18001f2eb  cmp     byte ptr [rcx+19h], 6
0x18001f2ef  jb      short loc_18001F305
0x18001f2f1  mov     edx, 1FBh
0x18001f2f6  mov     rcx, [rcx+10h]
0x18001f2fa  mov     r9d, ebx
0x18001f2fd  mov     r8, r14
0x18001f300  call    WPP_SF_d
0x18001f305  mov     eax, ebx
0x18001f307  add     rsp, 28h
0x18001f30b  pop     r14
0x18001f30d  pop     rdi
0x18001f30e  pop     rbp
0x18001f30f  pop     rbx
0x18001f310  retn
```
