# RasRequestNotification

- ea: `0x18001e870`
- end: `0x18001e9b8`
- name: `RasRequestNotification`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001e870`
- `0x180021b14`
- `0x1800225a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e8f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e8f4`

## pseudocode

```c
__int64 __fastcall RasRequestNotification(__int64 a1, __int64 a2, __int64 a3)
{
  PVOID *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  DWORD CurrentProcessId; // eax
  DWORD v9; // esi
  unsigned int v10; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 281, a3, a1, a2);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    v6 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 282;
LABEL_24:
      WPP_SF_d(v5[2], v7, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
      return v6;
    }
    return v6;
  }
  CurrentProcessId = GetCurrentProcessId();
  v9 = CurrentProcessId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      283,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  v10 = SubmitLocalRequest(0x1Eu, a1, a2, v9);
  v6 = v10;
  if ( v10 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_20;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 284, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 6u )
  {
    v7 = 285;
    goto LABEL_24;
  }
  return v6;
}

```

## disassembly

```asm
0x18001e870  push    rbx
0x18001e872  push    rsi
0x18001e873  push    rdi
0x18001e874  push    r14
0x18001e876  sub     rsp, 38h
0x18001e87a  mov     rdi, rdx
0x18001e87d  mov     rbx, rcx
0x18001e880  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e887  lea     r14, WPP_GLOBAL_Control
0x18001e88e  cmp     rcx, r14
0x18001e891  jz      short loc_18001E8B5
0x18001e893  test    byte ptr [rcx+1Ch], 40h
0x18001e897  jz      short loc_18001E8B5
0x18001e899  cmp     byte ptr [rcx+19h], 6
0x18001e89d  jb      short loc_18001E8B5
0x18001e89f  mov     rcx, [rcx+10h]
0x18001e8a3  mov     edx, 119h
0x18001e8a8  mov     r9, rbx
0x18001e8ab  mov     [rsp+58h+var_38], rdi
0x18001e8b0  call    WPP_SF_qq
0x18001e8b5  mov     rcx, rbx
0x18001e8b8  call    ValidatePortHandle
0x18001e8bd  test    eax, eax
0x18001e8bf  jnz     short loc_18001E8F4
0x18001e8c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8c8  mov     ebx, 259h
0x18001e8cd  cmp     rcx, r14
0x18001e8d0  jz      loc_18001E9AB
0x18001e8d6  test    byte ptr [rcx+1Ch], 40h
0x18001e8da  jz      loc_18001E9AB
0x18001e8e0  cmp     byte ptr [rcx+19h], 2
0x18001e8e4  jb      loc_18001E9AB
0x18001e8ea  mov     edx, 11Ah
0x18001e8ef  jmp     loc_18001E998
0x18001e8f4  call    cs:__imp_GetCurrentProcessId
0x18001e8fb  nop     dword ptr [rax+rax+00h]
0x18001e900  mov     esi, eax
0x18001e902  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e909  cmp     rcx, r14
0x18001e90c  jz      short loc_18001E932
0x18001e90e  test    byte ptr [rcx+1Ch], 40h
0x18001e912  jz      short loc_18001E932
0x18001e914  cmp     byte ptr [rcx+19h], 5
0x18001e918  jb      short loc_18001E932
0x18001e91a  mov     rcx, [rcx+10h]
0x18001e91e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e925  mov     edx, 11Bh
0x18001e92a  mov     r9d, eax
0x18001e92d  call    WPP_SF_d
0x18001e932  mov     ecx, 1Eh
0x18001e937  mov     r9d, esi
0x18001e93a  mov     r8, rdi
0x18001e93d  mov     rdx, rbx
0x18001e940  call    SubmitLocalRequest
0x18001e945  mov     ebx, eax
0x18001e947  test    eax, eax
0x18001e949  jz      short loc_18001E97B
0x18001e94b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e952  cmp     rcx, r14
0x18001e955  jz      short loc_18001E9AB
0x18001e957  test    byte ptr [rcx+1Ch], 40h
0x18001e95b  jz      short loc_18001E982
0x18001e95d  cmp     byte ptr [rcx+19h], 2
0x18001e961  jb      short loc_18001E982
0x18001e963  mov     rcx, [rcx+10h]
0x18001e967  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e96e  mov     edx, 11Ch
0x18001e973  mov     r9d, eax
0x18001e976  call    WPP_SF_d
0x18001e97b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e982  cmp     rcx, r14
0x18001e985  jz      short loc_18001E9AB
0x18001e987  test    byte ptr [rcx+1Ch], 40h
0x18001e98b  jz      short loc_18001E9AB
0x18001e98d  cmp     byte ptr [rcx+19h], 6
0x18001e991  jb      short loc_18001E9AB
0x18001e993  mov     edx, 11Dh
0x18001e998  mov     rcx, [rcx+10h]
0x18001e99c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e9a3  mov     r9d, ebx
0x18001e9a6  call    WPP_SF_d
0x18001e9ab  mov     eax, ebx
0x18001e9ad  add     rsp, 38h
0x18001e9b1  pop     r14
0x18001e9b3  pop     rdi
0x18001e9b4  pop     rsi
0x18001e9b5  pop     rbx
0x18001e9b6  retn
```
