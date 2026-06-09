# RasPortReserve

- ea: `0x18001c7b0`
- end: `0x18001c8c6`
- name: `RasPortReserve`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1800030d0`
- `0x18001c7b0`
- `0x180021ae4`
- `0x180021b14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c7f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c7f4`

## pseudocode

```c
__int64 __fastcall RasPortReserve(__int64 a1, __int64 a2)
{
  DWORD CurrentProcessId; // eax
  DWORD v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  CurrentProcessId = GetCurrentProcessId();
  v5 = CurrentProcessId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      102,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  v6 = SubmitLocalRequest(1u, a1, 0, v5, 0, a2);
  v7 = v6;
  if ( !v6 )
    goto LABEL_14;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
LABEL_14:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 104, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18001c7b0  push    rbx
0x18001c7b2  push    rsi
0x18001c7b3  push    rdi
0x18001c7b4  push    r14
0x18001c7b6  sub     rsp, 38h
0x18001c7ba  mov     rdi, rdx
0x18001c7bd  mov     rsi, rcx
0x18001c7c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7c7  lea     r14, WPP_GLOBAL_Control
0x18001c7ce  cmp     rcx, r14
0x18001c7d1  jz      short loc_18001C7F4
0x18001c7d3  test    byte ptr [rcx+1Ch], 40h
0x18001c7d7  jz      short loc_18001C7F4
0x18001c7d9  cmp     byte ptr [rcx+19h], 6
0x18001c7dd  jb      short loc_18001C7F4
0x18001c7df  mov     rcx, [rcx+10h]
0x18001c7e3  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c7ea  mov     edx, 65h ; 'e'
0x18001c7ef  call    WPP_SF_
0x18001c7f4  call    cs:__imp_GetCurrentProcessId
0x18001c7fb  nop     dword ptr [rax+rax+00h]
0x18001c800  mov     ebx, eax
0x18001c802  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c809  cmp     rcx, r14
0x18001c80c  jz      short loc_18001C832
0x18001c80e  test    byte ptr [rcx+1Ch], 40h
0x18001c812  jz      short loc_18001C832
0x18001c814  cmp     byte ptr [rcx+19h], 5
0x18001c818  jb      short loc_18001C832
0x18001c81a  mov     rcx, [rcx+10h]
0x18001c81e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c825  mov     edx, 66h ; 'f'
0x18001c82a  mov     r9d, eax
0x18001c82d  call    WPP_SF_d
0x18001c832  mov     ecx, 1
0x18001c837  mov     [rsp+58h+var_30], rdi
0x18001c83c  mov     r9d, ebx
0x18001c83f  mov     [rsp+58h+var_38], 0
0x18001c848  xor     r8d, r8d
0x18001c84b  mov     rdx, rsi
0x18001c84e  call    SubmitLocalRequest
0x18001c853  mov     ebx, eax
0x18001c855  test    eax, eax
0x18001c857  jz      short loc_18001C889
0x18001c859  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c860  cmp     rcx, r14
0x18001c863  jz      short loc_18001C8B9
0x18001c865  test    byte ptr [rcx+1Ch], 40h
0x18001c869  jz      short loc_18001C890
0x18001c86b  cmp     byte ptr [rcx+19h], 2
0x18001c86f  jb      short loc_18001C890
0x18001c871  mov     rcx, [rcx+10h]
0x18001c875  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c87c  mov     edx, 67h ; 'g'
0x18001c881  mov     r9d, eax
0x18001c884  call    WPP_SF_d
0x18001c889  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c890  cmp     rcx, r14
0x18001c893  jz      short loc_18001C8B9
0x18001c895  test    byte ptr [rcx+1Ch], 40h
0x18001c899  jz      short loc_18001C8B9
0x18001c89b  cmp     byte ptr [rcx+19h], 6
0x18001c89f  jb      short loc_18001C8B9
0x18001c8a1  mov     rcx, [rcx+10h]
0x18001c8a5  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c8ac  mov     edx, 68h ; 'h'
0x18001c8b1  mov     r9d, ebx
0x18001c8b4  call    WPP_SF_d
0x18001c8b9  mov     eax, ebx
0x18001c8bb  add     rsp, 38h
0x18001c8bf  pop     r14
0x18001c8c1  pop     rdi
0x18001c8c2  pop     rsi
0x18001c8c3  pop     rbx
0x18001c8c4  retn
```
