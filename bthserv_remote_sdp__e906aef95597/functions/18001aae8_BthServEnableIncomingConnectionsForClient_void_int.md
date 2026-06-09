# BthServEnableIncomingConnectionsForClient(void *,int)

- ea: `0x18001aae8`
- end: `0x18001ac5b`
- name: `?BthServEnableIncomingConnectionsForClient@@YAKPEAXH@Z`
- size: `371`
- prototype: `unsigned int __fastcall(void *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012f0c`
- `0x1800136e0`

## callees

- `0x1800120b8`
- `0x18001aae8`
- `0x18001addc`
- `0x18001b29c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac32`

## pseudocode

```c
__int64 __fastcall BthServEnableIncomingConnectionsForClient(_DWORD *a1, int a2)
{
  int v2; // ebp
  unsigned int v4; // ebx
  char v5; // di
  int v6; // edx
  int v7; // r8d
  int v8; // eax
  int v9; // eax
  int v10; // eax

  v2 = a2;
  v4 = 0;
  v5 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sql(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  EnterCriticalSection(&stru_1800470B0);
  v8 = a1[24];
  if ( v2 )
  {
    if ( !v8 )
    {
      v10 = dword_1800470DC;
      if ( !dword_1800470DC )
      {
        v4 = BthServSetConnectable(1);
        if ( v4 )
          goto LABEL_19;
        v10 = dword_1800470DC;
      }
      dword_1800470DC = v10 + 1;
      ++a1[24];
      goto LABEL_19;
    }
    goto LABEL_14;
  }
  if ( !v8 )
  {
LABEL_14:
    v4 = 87;
    goto LABEL_19;
  }
  v9 = dword_1800470DC;
  if ( dword_1800470DC == 1 )
  {
    BthServSetConnectable(0);
    v9 = dword_1800470DC;
  }
  dword_1800470DC = v9 - 1;
  --a1[24];
LABEL_19:
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    v5 = 0;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = v5;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  LeaveCriticalSection(&stru_1800470B0);
  return v4;
}

```

## disassembly

```asm
0x18001aae8  mov     [rsp+arg_0], rbx
0x18001aaed  mov     [rsp+arg_8], rbp
0x18001aaf2  mov     [rsp+arg_10], rsi
0x18001aaf7  push    rdi
0x18001aaf8  push    r14
0x18001aafa  push    r15
0x18001aafc  sub     rsp, 60h
0x18001ab00  mov     ebp, edx
0x18001ab02  mov     rsi, rcx
0x18001ab05  xor     ebx, ebx
0x18001ab07  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab0e  lea     r15, WPP_GLOBAL_Control
0x18001ab15  lea     edi, [rbx+1]
0x18001ab18  cmp     rcx, r15
0x18001ab1b  jz      short loc_18001AB28
0x18001ab1d  cmp     byte ptr [rcx+19h], 4
0x18001ab21  jb      short loc_18001AB28
0x18001ab23  mov     dl, dil
0x18001ab26  jmp     short loc_18001AB2A
0x18001ab28  xor     dl, dl
0x18001ab2a  lea     r14, WPP_RECORDER_INITIALIZED
0x18001ab31  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18001ab38  setnz   r8b
0x18001ab3c  test    dl, dl
0x18001ab3e  jnz     short loc_18001AB45
0x18001ab40  test    r8b, r8b
0x18001ab43  jz      short loc_18001AB62
0x18001ab45  mov     r9, [rcx+28h]
0x18001ab49  mov     rcx, [rcx+10h]
0x18001ab4d  mov     [rsp+78h+var_28], ebp
0x18001ab51  mov     [rsp+78h+var_30], rsi
0x18001ab56  mov     [rsp+78h+var_48], 12h
0x18001ab5d  call    WPP_RECORDER_AND_TRACE_SF_sql
0x18001ab62  lea     rcx, stru_1800470B0; lpCriticalSection
0x18001ab69  call    cs:__imp_EnterCriticalSection
0x18001ab70  nop     dword ptr [rax+rax+00h]
0x18001ab75  mov     eax, [rsi+60h]
0x18001ab78  test    ebp, ebp
0x18001ab7a  jnz     short loc_18001ABA7
0x18001ab7c  test    eax, eax
0x18001ab7e  jz      short loc_18001ABAB
0x18001ab80  mov     eax, cs:dword_1800470DC
0x18001ab86  cmp     eax, edi
0x18001ab88  jnz     short loc_18001AB97
0x18001ab8a  xor     ecx, ecx; int
0x18001ab8c  call    ?BthServSetConnectable@@YAKH@Z; BthServSetConnectable(int)
0x18001ab91  mov     eax, cs:dword_1800470DC
0x18001ab97  or      ecx, 0FFFFFFFFh
0x18001ab9a  add     eax, ecx
0x18001ab9c  mov     cs:dword_1800470DC, eax
0x18001aba2  add     [rsi+60h], ecx
0x18001aba5  jmp     short loc_18001ABDA
0x18001aba7  test    eax, eax
0x18001aba9  jz      short loc_18001ABB2
0x18001abab  mov     ebx, 57h ; 'W'
0x18001abb0  jmp     short loc_18001ABDA
0x18001abb2  mov     eax, cs:dword_1800470DC
0x18001abb8  test    eax, eax
0x18001abba  jnz     short loc_18001ABCF
0x18001abbc  mov     ecx, edi; int
0x18001abbe  call    ?BthServSetConnectable@@YAKH@Z; BthServSetConnectable(int)
0x18001abc3  mov     ebx, eax
0x18001abc5  test    eax, eax
0x18001abc7  jnz     short loc_18001ABDA
0x18001abc9  mov     eax, cs:dword_1800470DC
0x18001abcf  add     eax, edi
0x18001abd1  mov     cs:dword_1800470DC, eax
0x18001abd7  add     [rsi+60h], edi
0x18001abda  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abe1  cmp     rcx, r15
0x18001abe4  jz      short loc_18001ABEC
0x18001abe6  cmp     byte ptr [rcx+19h], 4
0x18001abea  jnb     short loc_18001ABEF
0x18001abec  xor     dil, dil
0x18001abef  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18001abf6  setnz   r8b
0x18001abfa  test    dil, dil
0x18001abfd  jnz     short loc_18001AC04
0x18001abff  test    r8b, r8b
0x18001ac02  jz      short loc_18001AC2B
0x18001ac04  mov     r9, [rcx+28h]
0x18001ac08  lea     rax, WPP_1e105cb0c669395e076f5c19399c2c56_Traceguids
0x18001ac0f  mov     rcx, [rcx+10h]
0x18001ac13  mov     dl, dil
0x18001ac16  mov     dword ptr [rsp+78h+var_30], ebx
0x18001ac1a  mov     [rsp+78h+var_40], rax
0x18001ac1f  mov     [rsp+78h+var_48], 13h
0x18001ac26  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001ac2b  lea     rcx, stru_1800470B0; lpCriticalSection
0x18001ac32  call    cs:__imp_LeaveCriticalSection
0x18001ac39  nop     dword ptr [rax+rax+00h]
0x18001ac3e  lea     r11, [rsp+78h+var_18]
0x18001ac43  mov     eax, ebx
0x18001ac45  mov     rbx, [r11+20h]
0x18001ac49  mov     rbp, [r11+28h]
0x18001ac4d  mov     rsi, [r11+30h]
0x18001ac51  mov     rsp, r11
0x18001ac54  pop     r15
0x18001ac56  pop     r14
0x18001ac58  pop     rdi
0x18001ac59  retn
```
