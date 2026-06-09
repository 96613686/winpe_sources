# RasPortReceive

- ea: `0x18001ba70`
- end: `0x18001bc25`
- name: `RasPortReceive`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001e0b0`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001ba70`
- `0x180021000`
- `0x180021990`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bb3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bb3f`

## pseudocode

```c
__int64 __fastcall RasPortReceive(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  PVOID *v9; // rcx
  unsigned int v10; // edi
  __int64 v11; // rdx
  DWORD CurrentProcessId; // esi
  unsigned int v13; // eax
  __int64 v15; // [rsp+20h] [rbp-58h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, a3, a1, a4, a5);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v10 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 601);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 6u )
      {
        v11 = 152;
LABEL_28:
        WPP_SF_d(v9[2], v11, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
        return v10;
      }
    }
    return v10;
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      153,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  LODWORD(v15) = a4;
  v13 = SubmitLocalRequest(7u, a1, a2 - 32, a3, v15, a5, CurrentProcessId);
  v10 = v13;
  if ( v13 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v10;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_24;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v13);
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 6u )
  {
    v11 = 155;
    goto LABEL_28;
  }
  return v10;
}

```

## disassembly

```asm
0x18001ba70  push    rbp
0x18001ba72  push    rsi
0x18001ba73  push    rdi
0x18001ba74  push    r13
0x18001ba76  push    r14
0x18001ba78  push    r15
0x18001ba7a  sub     rsp, 48h
0x18001ba7e  mov     ebp, r9d
0x18001ba81  mov     r15, r8
0x18001ba84  mov     r13, rdx
0x18001ba87  mov     rdi, rcx
0x18001ba8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba91  lea     rsi, WPP_GLOBAL_Control
0x18001ba98  mov     r14, [rsp+78h+arg_20]
0x18001baa0  cmp     rcx, rsi
0x18001baa3  jz      short loc_18001BACC
0x18001baa5  test    byte ptr [rcx+1Ch], 40h
0x18001baa9  jz      short loc_18001BACC
0x18001baab  cmp     byte ptr [rcx+19h], 6
0x18001baaf  jb      short loc_18001BACC
0x18001bab1  mov     rcx, [rcx+10h]
0x18001bab5  mov     edx, 96h
0x18001baba  mov     [rsp+78h+var_50], r14
0x18001babf  mov     dword ptr [rsp+78h+var_58], r9d
0x18001bac4  mov     r9, rdi
0x18001bac7  call    WPP_SF_qdq
0x18001bacc  mov     rcx, rdi
0x18001bacf  call    ValidatePortHandle
0x18001bad4  test    eax, eax
0x18001bad6  jnz     short loc_18001BB3F
0x18001bad8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001badf  mov     edi, 259h
0x18001bae4  cmp     rcx, rsi
0x18001bae7  jz      loc_18001BC15
0x18001baed  test    byte ptr [rcx+1Ch], 40h
0x18001baf1  jz      short loc_18001BB18
0x18001baf3  cmp     byte ptr [rcx+19h], 2
0x18001baf7  jb      short loc_18001BB18
0x18001baf9  mov     rcx, [rcx+10h]
0x18001bafd  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001bb04  mov     edx, 97h
0x18001bb09  mov     r9d, edi
0x18001bb0c  call    WPP_SF_d
0x18001bb11  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb18  cmp     rcx, rsi
0x18001bb1b  jz      loc_18001BC15
0x18001bb21  test    byte ptr [rcx+1Ch], 40h
0x18001bb25  jz      loc_18001BC15
0x18001bb2b  cmp     byte ptr [rcx+19h], 6
0x18001bb2f  jb      loc_18001BC15
0x18001bb35  mov     edx, 98h
0x18001bb3a  jmp     loc_18001BC02
0x18001bb3f  call    cs:__imp_GetCurrentProcessId
0x18001bb45  mov     esi, eax
0x18001bb47  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb4e  lea     rax, WPP_GLOBAL_Control
0x18001bb55  cmp     rcx, rax
0x18001bb58  jz      short loc_18001BB7E
0x18001bb5a  test    byte ptr [rcx+1Ch], 40h
0x18001bb5e  jz      short loc_18001BB7E
0x18001bb60  cmp     byte ptr [rcx+19h], 5
0x18001bb64  jb      short loc_18001BB7E
0x18001bb66  mov     rcx, [rcx+10h]
0x18001bb6a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001bb71  mov     edx, 99h
0x18001bb76  mov     r9d, esi
0x18001bb79  call    WPP_SF_d
0x18001bb7e  mov     [rsp+78h+var_48], esi
0x18001bb82  lea     r8, [r13-20h]
0x18001bb86  mov     [rsp+78h+var_50], r14
0x18001bb8b  mov     ecx, 7
0x18001bb90  mov     r9, r15
0x18001bb93  mov     dword ptr [rsp+78h+var_58], ebp
0x18001bb97  mov     rdx, rdi
0x18001bb9a  call    SubmitLocalRequest
0x18001bb9f  mov     edi, eax
0x18001bba1  test    eax, eax
0x18001bba3  jz      short loc_18001BBDE
0x18001bba5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbac  lea     rsi, WPP_GLOBAL_Control
0x18001bbb3  cmp     rcx, rsi
0x18001bbb6  jz      short loc_18001BC15
0x18001bbb8  test    byte ptr [rcx+1Ch], 40h
0x18001bbbc  jz      short loc_18001BBEC
0x18001bbbe  cmp     byte ptr [rcx+19h], 2
0x18001bbc2  jb      short loc_18001BBEC
0x18001bbc4  mov     rcx, [rcx+10h]
0x18001bbc8  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001bbcf  mov     edx, 9Ah
0x18001bbd4  mov     r9d, eax
0x18001bbd7  call    WPP_SF_d
0x18001bbdc  jmp     short loc_18001BBE5
0x18001bbde  lea     rsi, WPP_GLOBAL_Control
0x18001bbe5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbec  cmp     rcx, rsi
0x18001bbef  jz      short loc_18001BC15
0x18001bbf1  test    byte ptr [rcx+1Ch], 40h
0x18001bbf5  jz      short loc_18001BC15
0x18001bbf7  cmp     byte ptr [rcx+19h], 6
0x18001bbfb  jb      short loc_18001BC15
0x18001bbfd  mov     edx, 9Bh
0x18001bc02  mov     rcx, [rcx+10h]
0x18001bc06  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001bc0d  mov     r9d, edi
0x18001bc10  call    WPP_SF_d
0x18001bc15  mov     eax, edi
0x18001bc17  add     rsp, 48h
0x18001bc1b  pop     r15
0x18001bc1d  pop     r14
0x18001bc1f  pop     r13
0x18001bc21  pop     rdi
0x18001bc22  pop     rsi
0x18001bc23  pop     rbp
0x18001bc24  retn
```
