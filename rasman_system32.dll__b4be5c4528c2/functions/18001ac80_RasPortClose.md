# RasPortClose

- ea: `0x18001ac80`
- end: `0x18001ade7`
- name: `RasPortClose`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800179f0`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001ac80`
- `0x180021b14`
- `0x180021fd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001acc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001acc9`

## pseudocode

```c
__int64 __fastcall RasPortClose(__int64 a1)
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
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  CurrentProcessId = GetCurrentProcessId();
  v3 = CurrentProcessId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 601);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
      {
        v6 = 114;
LABEL_28:
        WPP_SF_d(v4[2], v6, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
        return v5;
      }
    }
    return v5;
  }
  v7 = SubmitLocalRequest(2u, a1, v3, 1);
  v5 = v7;
  if ( v7 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_24;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v6 = 116;
    goto LABEL_28;
  }
  return v5;
}

```

## disassembly

```asm
0x18001ac80  push    rbx
0x18001ac82  push    rsi
0x18001ac83  push    rdi
0x18001ac84  push    r14
0x18001ac86  push    r15
0x18001ac88  sub     rsp, 20h
0x18001ac8c  mov     rdi, rcx
0x18001ac8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac96  lea     r14, WPP_GLOBAL_Control
0x18001ac9d  lea     r15, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001aca4  cmp     rcx, r14
0x18001aca7  jz      short loc_18001ACC9
0x18001aca9  test    byte ptr [rcx+1Ch], 40h
0x18001acad  jz      short loc_18001ACC9
0x18001acaf  cmp     byte ptr [rcx+19h], 6
0x18001acb3  jb      short loc_18001ACC9
0x18001acb5  mov     rcx, [rcx+10h]
0x18001acb9  mov     edx, 6Fh ; 'o'
0x18001acbe  mov     r9, rdi
0x18001acc1  mov     r8, r15
0x18001acc4  call    WPP_SF_q
0x18001acc9  call    cs:__imp_GetCurrentProcessId
0x18001acd0  nop     dword ptr [rax+rax+00h]
0x18001acd5  mov     esi, eax
0x18001acd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acde  cmp     rcx, r14
0x18001ace1  jz      short loc_18001AD03
0x18001ace3  test    byte ptr [rcx+1Ch], 40h
0x18001ace7  jz      short loc_18001AD03
0x18001ace9  cmp     byte ptr [rcx+19h], 5
0x18001aced  jb      short loc_18001AD03
0x18001acef  mov     rcx, [rcx+10h]
0x18001acf3  mov     edx, 70h ; 'p'
0x18001acf8  mov     r9d, eax
0x18001acfb  mov     r8, r15
0x18001acfe  call    WPP_SF_d
0x18001ad03  mov     rcx, rdi
0x18001ad06  call    ValidatePortHandle
0x18001ad0b  test    eax, eax
0x18001ad0d  jnz     short loc_18001AD67
0x18001ad0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad16  mov     edi, 259h
0x18001ad1b  cmp     rcx, r14
0x18001ad1e  jz      loc_18001ADD8
0x18001ad24  test    byte ptr [rcx+1Ch], 40h
0x18001ad28  jz      short loc_18001AD4B
0x18001ad2a  lea     ebx, [rax+2]
0x18001ad2d  cmp     [rcx+19h], bl
0x18001ad30  jb      short loc_18001AD4B
0x18001ad32  mov     rcx, [rcx+10h]
0x18001ad36  lea     edx, [rax+71h]
0x18001ad39  mov     r9d, edi
0x18001ad3c  mov     r8, r15
0x18001ad3f  call    WPP_SF_d
0x18001ad44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad4b  cmp     rcx, r14
0x18001ad4e  jz      loc_18001ADD8
0x18001ad54  test    byte ptr [rcx+1Ch], 40h
0x18001ad58  jz      short loc_18001ADD8
0x18001ad5a  cmp     byte ptr [rcx+19h], 6
0x18001ad5e  jb      short loc_18001ADD8
0x18001ad60  mov     edx, 72h ; 'r'
0x18001ad65  jmp     short loc_18001ADC9
0x18001ad67  mov     ebx, 2
0x18001ad6c  mov     r8d, esi
0x18001ad6f  mov     rdx, rdi
0x18001ad72  mov     ecx, ebx
0x18001ad74  lea     r9d, [rbx-1]
0x18001ad78  call    SubmitLocalRequest
0x18001ad7d  mov     edi, eax
0x18001ad7f  test    eax, eax
0x18001ad81  jz      short loc_18001ADAC
0x18001ad83  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad8a  cmp     rcx, r14
0x18001ad8d  jz      short loc_18001ADD8
0x18001ad8f  test    byte ptr [rcx+1Ch], 40h
0x18001ad93  jz      short loc_18001ADB3
0x18001ad95  cmp     [rcx+19h], bl
0x18001ad98  jb      short loc_18001ADB3
0x18001ad9a  mov     rcx, [rcx+10h]
0x18001ad9e  lea     edx, [rbx+71h]
0x18001ada1  mov     r9d, eax
0x18001ada4  mov     r8, r15
0x18001ada7  call    WPP_SF_d
0x18001adac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adb3  cmp     rcx, r14
0x18001adb6  jz      short loc_18001ADD8
0x18001adb8  test    byte ptr [rcx+1Ch], 40h
0x18001adbc  jz      short loc_18001ADD8
0x18001adbe  cmp     byte ptr [rcx+19h], 6
0x18001adc2  jb      short loc_18001ADD8
0x18001adc4  mov     edx, 74h ; 't'
0x18001adc9  mov     rcx, [rcx+10h]
0x18001adcd  mov     r9d, edi
0x18001add0  mov     r8, r15
0x18001add3  call    WPP_SF_d
0x18001add8  mov     eax, edi
0x18001adda  add     rsp, 20h
0x18001adde  pop     r15
0x18001ade0  pop     r14
0x18001ade2  pop     rdi
0x18001ade3  pop     rsi
0x18001ade4  pop     rbx
0x18001ade5  retn
```
