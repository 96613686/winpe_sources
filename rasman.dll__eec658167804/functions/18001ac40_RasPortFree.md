# RasPortFree

- ea: `0x18001ac40`
- end: `0x18001ad9f`
- name: `RasPortFree`
- size: `351`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001ac40`
- `0x180021000`
- `0x180021488`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ac89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ac89`

## pseudocode

```c
__int64 __fastcall RasPortFree(__int64 a1)
{
  DWORD CurrentProcessId; // eax
  DWORD v3; // esi
  PVOID *v4; // rcx
  unsigned int v5; // edi
  __int64 v6; // rdx
  unsigned int v7; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  CurrentProcessId = GetCurrentProcessId();
  v3 = CurrentProcessId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      106,
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 601);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
      {
        v6 = 108;
LABEL_28:
        WPP_SF_d(v4[2], v6, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
        return v5;
      }
    }
    return v5;
  }
  v7 = SubmitLocalRequest(2u, a1, v3, 0);
  v5 = v7;
  if ( v7 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_24;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v6 = 110;
    goto LABEL_28;
  }
  return v5;
}

```

## disassembly

```asm
0x18001ac40  push    rbx
0x18001ac42  push    rsi
0x18001ac43  push    rdi
0x18001ac44  push    r14
0x18001ac46  push    r15
0x18001ac48  sub     rsp, 20h
0x18001ac4c  mov     rdi, rcx
0x18001ac4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac56  lea     r14, WPP_GLOBAL_Control
0x18001ac5d  lea     r15, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ac64  cmp     rcx, r14
0x18001ac67  jz      short loc_18001AC89
0x18001ac69  test    byte ptr [rcx+1Ch], 40h
0x18001ac6d  jz      short loc_18001AC89
0x18001ac6f  cmp     byte ptr [rcx+19h], 6
0x18001ac73  jb      short loc_18001AC89
0x18001ac75  mov     rcx, [rcx+10h]
0x18001ac79  mov     edx, 69h ; 'i'
0x18001ac7e  mov     r9, rdi
0x18001ac81  mov     r8, r15
0x18001ac84  call    WPP_SF_q
0x18001ac89  call    cs:__imp_GetCurrentProcessId
0x18001ac8f  mov     esi, eax
0x18001ac91  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac98  cmp     rcx, r14
0x18001ac9b  jz      short loc_18001ACBD
0x18001ac9d  test    byte ptr [rcx+1Ch], 40h
0x18001aca1  jz      short loc_18001ACBD
0x18001aca3  cmp     byte ptr [rcx+19h], 5
0x18001aca7  jb      short loc_18001ACBD
0x18001aca9  mov     rcx, [rcx+10h]
0x18001acad  mov     edx, 6Ah ; 'j'
0x18001acb2  mov     r9d, eax
0x18001acb5  mov     r8, r15
0x18001acb8  call    WPP_SF_d
0x18001acbd  mov     rcx, rdi
0x18001acc0  call    ValidatePortHandle
0x18001acc5  test    eax, eax
0x18001acc7  jnz     short loc_18001AD21
0x18001acc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acd0  mov     edi, 259h
0x18001acd5  cmp     rcx, r14
0x18001acd8  jz      loc_18001AD91
0x18001acde  test    byte ptr [rcx+1Ch], 40h
0x18001ace2  jz      short loc_18001AD05
0x18001ace4  lea     ebx, [rax+2]
0x18001ace7  cmp     [rcx+19h], bl
0x18001acea  jb      short loc_18001AD05
0x18001acec  mov     rcx, [rcx+10h]
0x18001acf0  lea     edx, [rax+6Bh]
0x18001acf3  mov     r9d, edi
0x18001acf6  mov     r8, r15
0x18001acf9  call    WPP_SF_d
0x18001acfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad05  cmp     rcx, r14
0x18001ad08  jz      loc_18001AD91
0x18001ad0e  test    byte ptr [rcx+1Ch], 40h
0x18001ad12  jz      short loc_18001AD91
0x18001ad14  cmp     byte ptr [rcx+19h], 6
0x18001ad18  jb      short loc_18001AD91
0x18001ad1a  mov     edx, 6Ch ; 'l'
0x18001ad1f  jmp     short loc_18001AD82
0x18001ad21  mov     ebx, 2
0x18001ad26  xor     r9d, r9d
0x18001ad29  mov     ecx, ebx
0x18001ad2b  mov     r8d, esi
0x18001ad2e  mov     rdx, rdi
0x18001ad31  call    SubmitLocalRequest
0x18001ad36  mov     edi, eax
0x18001ad38  test    eax, eax
0x18001ad3a  jz      short loc_18001AD65
0x18001ad3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad43  cmp     rcx, r14
0x18001ad46  jz      short loc_18001AD91
0x18001ad48  test    byte ptr [rcx+1Ch], 40h
0x18001ad4c  jz      short loc_18001AD6C
0x18001ad4e  cmp     [rcx+19h], bl
0x18001ad51  jb      short loc_18001AD6C
0x18001ad53  mov     rcx, [rcx+10h]
0x18001ad57  lea     edx, [rbx+6Bh]
0x18001ad5a  mov     r9d, eax
0x18001ad5d  mov     r8, r15
0x18001ad60  call    WPP_SF_d
0x18001ad65  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad6c  cmp     rcx, r14
0x18001ad6f  jz      short loc_18001AD91
0x18001ad71  test    byte ptr [rcx+1Ch], 40h
0x18001ad75  jz      short loc_18001AD91
0x18001ad77  cmp     byte ptr [rcx+19h], 6
0x18001ad7b  jb      short loc_18001AD91
0x18001ad7d  mov     edx, 6Eh ; 'n'
0x18001ad82  mov     rcx, [rcx+10h]
0x18001ad86  mov     r9d, edi
0x18001ad89  mov     r8, r15
0x18001ad8c  call    WPP_SF_d
0x18001ad91  mov     eax, edi
0x18001ad93  add     rsp, 20h
0x18001ad97  pop     r15
0x18001ad99  pop     r14
0x18001ad9b  pop     rdi
0x18001ad9c  pop     rsi
0x18001ad9d  pop     rbx
0x18001ad9e  retn
```
