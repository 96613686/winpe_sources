# DfdATA::GetSMARTInfo(ulong *,ulong *)

- ea: `0x180007c6c`
- end: `0x180007eff`
- name: `?GetSMARTInfo@DfdATA@@QEAAKPEAK0@Z`
- size: `659`
- prototype: `__int64 __fastcall(DfdATA *this, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800037bc`

## callees

- `0x180002c68`
- `0x180002c90`
- `0x180002d64`
- `0x180007c6c`
- `0x180007f08`
- `0x1800081d8`
- `0x18000833b`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180007c99`
- `KERNEL32!HeapAlloc` at `0x180007c99`
- `KERNEL32!GetProcessHeap` at `0x180007c85`
- `KERNEL32!GetProcessHeap` at `0x180007ed8`
- `KERNEL32!GetProcessHeap` at `0x180007c85`
- `KERNEL32!GetProcessHeap` at `0x180007ed8`
- `KERNEL32!HeapFree` at `0x180007ee6`
- `KERNEL32!HeapFree` at `0x180007ee6`

## pseudocode

```c
__int64 __fastcall DfdATA::GetSMARTInfo(DfdATA *this, unsigned int *a2, unsigned int *a3)
{
  HANDLE ProcessHeap; // rax
  struct _SENDCMDOUTPARAMS *v7; // rax
  unsigned int v8; // r8d
  struct _SENDCMDOUTPARAMS *v9; // rsi
  unsigned int v10; // r14d
  unsigned int SMARTLog; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  __int64 v19; // r8
  char cBufferSize; // al
  HANDLE v21; // rax

  ProcessHeap = GetProcessHeap();
  v7 = (struct _SENDCMDOUTPARAMS *)HeapAlloc(ProcessHeap, 8u, 0x221u);
  v9 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_47546f163ca83b4871ae2173b5583170_Traceguids, v7, 545);
    SMARTLog = DfdATA::ReadSMARTLog(this, v9, v8, 0);
    v10 = SMARTLog;
    if ( SMARTLog )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_39;
      v13 = 12;
      goto LABEL_12;
    }
    if ( BYTE1(v9[1].cBufferSize) == 1 )
    {
      memset_0(v9, 0, 0x221u);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_47546f163ca83b4871ae2173b5583170_Traceguids, v9, 545);
      SMARTLog = DfdATA::ReadSMARTLog(this, v9, v17, 1u);
      v10 = SMARTLog;
      if ( SMARTLog )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_39;
        v13 = 15;
LABEL_12:
        v14 = SMARTLog;
LABEL_13:
        WPP_SF_d(v12[2], v13, &WPP_47546f163ca83b4871ae2173b5583170_Traceguids, v14);
        goto LABEL_39;
      }
      if ( v9->bBuffer[0] != 1 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_39;
        v14 = v9->bBuffer[0];
        v13 = 16;
        goto LABEL_13;
      }
      if ( LOBYTE(v9[1].cBufferSize) )
      {
        *a2 = BYTE1(v9[27].DriverStatus.dwReserved[0]) + (BYTE2(v9[27].DriverStatus.dwReserved[0]) << 8);
        cBufferSize = v9[1].cBufferSize;
        if ( cBufferSize )
          *a3 = *((unsigned __int8 *)&v9[6].cBufferSize + (unsigned __int8)(90 * (cBufferSize - 1) + 2) + 2)
              + (*((unsigned __int8 *)&v9[6].cBufferSize + (unsigned __int8)(90 * (cBufferSize - 1) + 2) + 3) << 8);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, LOBYTE(v9[1].cBufferSize), *a2, *a3);
        goto LABEL_39;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_39:
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v9);
        return v10;
      }
      v16 = 17;
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_39;
      v16 = 13;
    }
    WPP_SF_(v15[2], v16, &WPP_47546f163ca83b4871ae2173b5583170_Traceguids);
    goto LABEL_39;
  }
  v10 = 14;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_47546f163ca83b4871ae2173b5583170_Traceguids, 14);
  return v10;
}

```

## disassembly

```asm
0x180007c6c  push    rbp
0x180007c6e  push    rsi
0x180007c6f  push    rdi
0x180007c70  push    r12
0x180007c72  push    r13
0x180007c74  push    r14
0x180007c76  push    r15
0x180007c78  sub     rsp, 30h
0x180007c7c  mov     r13, r8
0x180007c7f  mov     r12, rdx
0x180007c82  mov     r15, rcx
0x180007c85  call    cs:__imp_GetProcessHeap
0x180007c8b  mov     edx, 8; dwFlags
0x180007c90  mov     r8d, 221h; dwBytes
0x180007c96  mov     rcx, rax; hHeap
0x180007c99  call    cs:__imp_HeapAlloc
0x180007c9f  mov     rsi, rax
0x180007ca2  test    rax, rax
0x180007ca5  jnz     short loc_180007CE7
0x180007ca7  lea     r14d, [rax+0Eh]
0x180007cab  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cb2  lea     rdi, WPP_GLOBAL_Control
0x180007cb9  cmp     rcx, rdi
0x180007cbc  jz      loc_180007EEC
0x180007cc2  test    byte ptr [rcx+1Ch], 1
0x180007cc6  jz      loc_180007EEC
0x180007ccc  mov     rcx, [rcx+10h]
0x180007cd0  lea     edx, [rax+0Ah]
0x180007cd3  mov     r9d, r14d
0x180007cd6  lea     r8, WPP_47546f163ca83b4871ae2173b5583170_Traceguids
0x180007cdd  call    WPP_SF_d
0x180007ce2  jmp     loc_180007EEC
0x180007ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cee  lea     rdi, WPP_GLOBAL_Control
0x180007cf5  lea     rbp, WPP_47546f163ca83b4871ae2173b5583170_Traceguids
0x180007cfc  cmp     rcx, rdi
0x180007cff  jz      short loc_180007D23
0x180007d01  test    byte ptr [rcx+1Ch], 4
0x180007d05  jz      short loc_180007D23
0x180007d07  mov     rcx, [rcx+10h]
0x180007d0b  mov     edx, 0Bh
0x180007d10  mov     r9, rsi
0x180007d13  mov     [rsp+68h+var_48], 221h
0x180007d1b  mov     r8, rbp
0x180007d1e  call    WPP_SF_qD
0x180007d23  xor     r9d, r9d; unsigned __int8
0x180007d26  mov     rdx, rsi; struct _SENDCMDOUTPARAMS *
0x180007d29  mov     rcx, r15; this
0x180007d2c  call    ?ReadSMARTLog@DfdATA@@AEAAKPEAU_SENDCMDOUTPARAMS@@KE@Z; DfdATA::ReadSMARTLog(_SENDCMDOUTPARAMS *,ulong,uchar)
0x180007d31  mov     r14d, eax
0x180007d34  test    eax, eax
0x180007d36  jz      short loc_180007D6B
0x180007d38  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d3f  cmp     rcx, rdi
0x180007d42  jz      loc_180007ED8
0x180007d48  test    byte ptr [rcx+1Ch], 1
0x180007d4c  jz      loc_180007ED8
0x180007d52  mov     edx, 0Ch
0x180007d57  mov     r9d, eax
0x180007d5a  mov     rcx, [rcx+10h]
0x180007d5e  mov     r8, rbp
0x180007d61  call    WPP_SF_d
0x180007d66  jmp     loc_180007ED8
0x180007d6b  cmp     byte ptr [rsi+12h], 1
0x180007d6f  jz      short loc_180007DA1
0x180007d71  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d78  cmp     rcx, rdi
0x180007d7b  jz      loc_180007ED8
0x180007d81  test    byte ptr [rcx+1Ch], 1
0x180007d85  jz      loc_180007ED8
0x180007d8b  mov     edx, 0Dh
0x180007d90  mov     rcx, [rcx+10h]
0x180007d94  mov     r8, rbp
0x180007d97  call    WPP_SF_
0x180007d9c  jmp     loc_180007ED8
0x180007da1  xor     edx, edx; Val
0x180007da3  mov     r8d, 221h; Size
0x180007da9  mov     rcx, rsi; void *
0x180007dac  call    memset_0
0x180007db1  mov     rcx, cs:WPP_GLOBAL_Control
0x180007db8  cmp     rcx, rdi
0x180007dbb  jz      short loc_180007DDF
0x180007dbd  test    byte ptr [rcx+1Ch], 4
0x180007dc1  jz      short loc_180007DDF
0x180007dc3  mov     rcx, [rcx+10h]
0x180007dc7  mov     edx, 0Eh
0x180007dcc  mov     r9, rsi
0x180007dcf  mov     [rsp+68h+var_48], 221h
0x180007dd7  mov     r8, rbp
0x180007dda  call    WPP_SF_qD
0x180007ddf  mov     r9b, 1; unsigned __int8
0x180007de2  mov     rdx, rsi; struct _SENDCMDOUTPARAMS *
0x180007de5  mov     rcx, r15; this
0x180007de8  call    ?ReadSMARTLog@DfdATA@@AEAAKPEAU_SENDCMDOUTPARAMS@@KE@Z; DfdATA::ReadSMARTLog(_SENDCMDOUTPARAMS *,ulong,uchar)
0x180007ded  mov     r14d, eax
0x180007df0  test    eax, eax
0x180007df2  jz      short loc_180007E18
0x180007df4  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dfb  cmp     rcx, rdi
0x180007dfe  jz      loc_180007ED8
0x180007e04  test    byte ptr [rcx+1Ch], 1
0x180007e08  jz      loc_180007ED8
0x180007e0e  mov     edx, 0Fh
0x180007e13  jmp     loc_180007D57
0x180007e18  cmp     byte ptr [rsi+10h], 1
0x180007e1c  jz      short loc_180007E47
0x180007e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e25  cmp     rcx, rdi
0x180007e28  jz      loc_180007ED8
0x180007e2e  test    byte ptr [rcx+1Ch], 1
0x180007e32  jz      loc_180007ED8
0x180007e38  movzx   r9d, byte ptr [rsi+10h]
0x180007e3d  mov     edx, 10h
0x180007e42  jmp     loc_180007D5A
0x180007e47  cmp     byte ptr [rsi+11h], 0
0x180007e4b  jnz     short loc_180007E69
0x180007e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e54  cmp     rcx, rdi
0x180007e57  jz      short loc_180007ED8
0x180007e59  test    byte ptr [rcx+1Ch], 1
0x180007e5d  jz      short loc_180007ED8
0x180007e5f  mov     edx, 11h
0x180007e64  jmp     loc_180007D90
0x180007e69  movzx   eax, byte ptr [rsi+1D4h]
0x180007e70  movzx   ecx, byte ptr [rsi+1D5h]
0x180007e77  shl     ecx, 8
0x180007e7a  add     ecx, eax
0x180007e7c  mov     [r12], ecx
0x180007e80  mov     al, [rsi+11h]
0x180007e83  test    al, al
0x180007e85  jz      short loc_180007EA8
0x180007e87  dec     al
0x180007e89  movzx   eax, al
0x180007e8c  imul    ecx, eax, 5Ah ; 'Z'
0x180007e8f  add     cl, 2
0x180007e92  movzx   eax, cl
0x180007e95  movzx   ecx, byte ptr [rax+rsi+69h]
0x180007e9a  movzx   eax, byte ptr [rax+rsi+68h]
0x180007e9f  shl     ecx, 8
0x180007ea2  add     ecx, eax
0x180007ea4  mov     [r13+0], ecx
0x180007ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x180007eaf  cmp     rcx, rdi
0x180007eb2  jz      short loc_180007ED8
0x180007eb4  test    byte ptr [rcx+1Ch], 4
0x180007eb8  jz      short loc_180007ED8
0x180007eba  mov     eax, [r13+0]
0x180007ebe  movzx   r9d, byte ptr [rsi+11h]
0x180007ec3  mov     rcx, [rcx+10h]
0x180007ec7  mov     [rsp+68h+var_40], eax
0x180007ecb  mov     eax, [r12]
0x180007ecf  mov     [rsp+68h+var_48], eax
0x180007ed3  call    WPP_SF_ddd
0x180007ed8  call    cs:__imp_GetProcessHeap
0x180007ede  mov     r8, rsi; lpMem
0x180007ee1  xor     edx, edx; dwFlags
0x180007ee3  mov     rcx, rax; hHeap
0x180007ee6  call    cs:__imp_HeapFree
0x180007eec  mov     eax, r14d
0x180007eef  add     rsp, 30h
0x180007ef3  pop     r15
0x180007ef5  pop     r14
0x180007ef7  pop     r13
0x180007ef9  pop     r12
0x180007efb  pop     rdi
0x180007efc  pop     rsi
0x180007efd  pop     rbp
0x180007efe  retn
```
