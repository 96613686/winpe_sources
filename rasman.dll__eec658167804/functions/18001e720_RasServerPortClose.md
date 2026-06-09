# RasServerPortClose

- ea: `0x18001e720`
- end: `0x18001e87b`
- name: `RasServerPortClose`
- size: `347`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001e720`
- `0x180021000`
- `0x180021488`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e767`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e767`

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
0x18001e720  push    rbx
0x18001e722  push    rbp
0x18001e723  push    rdi
0x18001e724  push    r14
0x18001e726  sub     rsp, 28h
0x18001e72a  mov     rbx, rcx
0x18001e72d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e734  lea     rbp, WPP_GLOBAL_Control
0x18001e73b  lea     r14, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e742  cmp     rcx, rbp
0x18001e745  jz      short loc_18001E767
0x18001e747  test    byte ptr [rcx+1Ch], 40h
0x18001e74b  jz      short loc_18001E767
0x18001e74d  cmp     byte ptr [rcx+19h], 6
0x18001e751  jb      short loc_18001E767
0x18001e753  mov     rcx, [rcx+10h]
0x18001e757  mov     edx, 1F6h
0x18001e75c  mov     r9, rbx
0x18001e75f  mov     r8, r14
0x18001e762  call    WPP_SF_q
0x18001e767  call    cs:__imp_GetCurrentProcessId
0x18001e76d  mov     edi, eax
0x18001e76f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e776  cmp     rcx, rbp
0x18001e779  jz      short loc_18001E79B
0x18001e77b  test    byte ptr [rcx+1Ch], 40h
0x18001e77f  jz      short loc_18001E79B
0x18001e781  cmp     byte ptr [rcx+19h], 5
0x18001e785  jb      short loc_18001E79B
0x18001e787  mov     rcx, [rcx+10h]
0x18001e78b  mov     edx, 1F7h
0x18001e790  mov     r9d, eax
0x18001e793  mov     r8, r14
0x18001e796  call    WPP_SF_d
0x18001e79b  mov     rcx, rbx
0x18001e79e  call    ValidatePortHandle
0x18001e7a3  test    eax, eax
0x18001e7a5  jnz     short loc_18001E7FD
0x18001e7a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e7ae  mov     ebx, 259h
0x18001e7b3  cmp     rcx, rbp
0x18001e7b6  jz      loc_18001E86F
0x18001e7bc  test    byte ptr [rcx+1Ch], 40h
0x18001e7c0  jz      short loc_18001E7E1
0x18001e7c2  cmp     byte ptr [rcx+19h], 2
0x18001e7c6  jb      short loc_18001E7E1
0x18001e7c8  mov     rcx, [rcx+10h]
0x18001e7cc  lea     edx, [rbx-61h]
0x18001e7cf  mov     r9d, ebx
0x18001e7d2  mov     r8, r14
0x18001e7d5  call    WPP_SF_d
0x18001e7da  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e7e1  cmp     rcx, rbp
0x18001e7e4  jz      loc_18001E86F
0x18001e7ea  test    byte ptr [rcx+1Ch], 40h
0x18001e7ee  jz      short loc_18001E86F
0x18001e7f0  cmp     byte ptr [rcx+19h], 6
0x18001e7f4  jb      short loc_18001E86F
0x18001e7f6  mov     edx, 1F9h
0x18001e7fb  jmp     short loc_18001E860
0x18001e7fd  mov     ecx, 51h ; 'Q'
0x18001e802  mov     r8d, edi
0x18001e805  mov     rdx, rbx
0x18001e808  lea     r9d, [rcx-50h]
0x18001e80c  call    SubmitLocalRequest
0x18001e811  mov     ebx, eax
0x18001e813  test    eax, eax
0x18001e815  jz      short loc_18001E843
0x18001e817  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e81e  cmp     rcx, rbp
0x18001e821  jz      short loc_18001E86F
0x18001e823  test    byte ptr [rcx+1Ch], 40h
0x18001e827  jz      short loc_18001E84A
0x18001e829  cmp     byte ptr [rcx+19h], 2
0x18001e82d  jb      short loc_18001E84A
0x18001e82f  mov     rcx, [rcx+10h]
0x18001e833  mov     edx, 1FAh
0x18001e838  mov     r9d, eax
0x18001e83b  mov     r8, r14
0x18001e83e  call    WPP_SF_d
0x18001e843  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e84a  cmp     rcx, rbp
0x18001e84d  jz      short loc_18001E86F
0x18001e84f  test    byte ptr [rcx+1Ch], 40h
0x18001e853  jz      short loc_18001E86F
0x18001e855  cmp     byte ptr [rcx+19h], 6
0x18001e859  jb      short loc_18001E86F
0x18001e85b  mov     edx, 1FBh
0x18001e860  mov     rcx, [rcx+10h]
0x18001e864  mov     r9d, ebx
0x18001e867  mov     r8, r14
0x18001e86a  call    WPP_SF_d
0x18001e86f  mov     eax, ebx
0x18001e871  add     rsp, 28h
0x18001e875  pop     r14
0x18001e877  pop     rdi
0x18001e878  pop     rbp
0x18001e879  pop     rbx
0x18001e87a  retn
```
