# QuicConnRecvDatagramBatch

- ea: `0x140012c80`
- end: `0x140012f06`
- name: `QuicConnRecvDatagramBatch`
- size: `646`
- prototype: `char __fastcall(__int64, __int64, unsigned __int8, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140015480`

## callees

- `0x1400108c0`
- `0x140012630`
- `0x140012c80`
- `0x140012f10`
- `0x140013200`
- `0x140026a88`
- `0x140034838`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140012cf7`
- `ntoskrnl!_snprintf_s` at `0x140012cf7`

## string_xrefs

- `0x140012d6a`: `Failed to compute HP mask`

## pseudocode

```c
char __fastcall QuicConnRecvDatagramBatch(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6)
{
  _QWORD *v6; // r14
  __int64 v7; // rsi
  __int64 v9; // rdi
  __int64 v10; // r12
  int v11; // ebp
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  char *v15; // r15
  __int64 v16; // rdi
  unsigned int v17; // ebp
  unsigned int v18; // edx
  char v19; // al
  char v20; // cl
  __int64 v22; // [rsp+30h] [rbp-168h] BYREF
  char v23[128]; // [rsp+40h] [rbp-158h] BYREF
  char DstBuf[128]; // [rsp+C0h] [rbp-D8h] BYREF

  v6 = a4;
  v7 = a2;
  v9 = *a4;
  v10 = a3;
  v11 = a3;
  v22 = a2;
  if ( (byte_14005C48C & 1) != 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Batch Recv %u UDP datagrams", a3);
    McTemplateU0ps_EtwWriteTransfer(v12, QuicConnLogVerbose, a1, DstBuf);
  }
  v13 = *(_QWORD *)(a1 + 8LL * *(int *)(v9 + 88) + 2872);
  if ( v13 )
  {
    if ( (*(_BYTE *)(v9 + 92) & 0x40) != 0 && (*(_BYTE *)(a1 + 249) & 8) != 0 )
    {
      LODWORD(v14) = CxPlatHpComputeMask(*(_QWORD *)(v13 + 16), (unsigned __int8)v10, a5, v23);
      if ( (int)v14 < 0 )
      {
        LOBYTE(v14) = QuicPacketLogDrop(a1, v9, "Failed to compute HP mask");
        return v14;
      }
    }
    else
    {
      LOBYTE(v14) = (unsigned __int8)memset(v23, 0, (unsigned int)(16 * v11));
    }
    if ( (_BYTE)v10 )
    {
      v15 = v23;
      do
      {
        v16 = *v6;
        v17 = *(_BYTE *)(*v6 + 28LL) & 3;
        LOBYTE(v14) = QuicConnRecvPrepareDecrypt(a1, *v6, v15);
        if ( (_BYTE)v14 && (LOBYTE(v14) = QuicConnRecvDecryptAndAuthenticate(a1, v7, v16), (_BYTE)v14) )
        {
          LOBYTE(v14) = QuicConnRecvFrames(a1, v7, v16, v17);
          if ( (_BYTE)v14 )
          {
            QuicConnRecvPostProcessing(a1, &v22, v16);
            v7 = v22;
            *(_BYTE *)a6 |= (*(_BYTE *)(v16 + 93) & 2) != 0;
            v14 = *(_QWORD *)(a1 + 80);
            if ( v14 )
            {
              if ( (*(_BYTE *)(v14 + 16) & 2) == 0
                && (*(_BYTE *)(v7 + 1) & 2) != 0
                && (*(_BYTE *)(v7 + 2) & 4) == 0
                && (*(_BYTE *)(v16 + 93) & 2) != 0 )
              {
                v18 = *(unsigned __int16 *)(*v6 + 26LL) % (unsigned int)(unsigned __int16)word_14005C55C;
                LODWORD(v14) = *(unsigned __int16 *)(a6 + 2);
                if ( v18 != (_DWORD)v14 )
                {
                  *(_WORD *)(a6 + 2) = v18;
                  *(_BYTE *)(a6 + 1) = 1;
                  *(_BYTE *)(v7 + 2) |= 4u;
                }
              }
            }
            if ( (*(_BYTE *)(v16 + 92) & 4) != 0 && (*(_BYTE *)(v16 + 93) & 4) != 0 )
            {
              v19 = **(_BYTE **)(v16 + 56);
              if ( *(_DWORD *)a1 == 4 )
              {
                LOBYTE(v14) = *(_BYTE *)(v7 + 1) & 0x7F | (4 * (v19 & 0xE0));
                *(_BYTE *)(v7 + 1) = v14;
              }
              else
              {
                LOBYTE(v14) = ~(4 * v19);
                *(_BYTE *)(v7 + 1) = v14 ^ (*(_BYTE *)(v7 + 1) ^ v14) & 0x7F;
              }
            }
          }
        }
        else
        {
          v20 = *(_BYTE *)(a1 + 251);
          if ( (v20 & 0x40) != 0 && v20 >= 0 )
          {
            LODWORD(v14) = *(_DWORD *)(a1 + 3884);
            *(_BYTE *)(a1 + 251) = v20 & 0xBF;
            *(_DWORD *)(a1 + 3636) = v14;
          }
        }
        v15 += 16;
        ++v6;
        --v10;
      }
      while ( v10 );
    }
  }
  else
  {
    LOBYTE(v14) = QuicPacketLogDrop(a1, v9, "Key no longer accepted (batch)");
  }
  return v14;
}

```

## disassembly

```asm
0x140012c80  push    rbx
0x140012c82  push    rbp
0x140012c83  push    rsi
0x140012c84  push    rdi
0x140012c85  push    r12
0x140012c87  push    r13
0x140012c89  push    r14
0x140012c8b  push    r15
0x140012c8d  sub     rsp, 158h
0x140012c94  mov     rax, cs:__security_cookie
0x140012c9b  xor     rax, rsp
0x140012c9e  mov     [rsp+198h+var_58], rax
0x140012ca6  test    cs:byte_14005C48C, 1
0x140012cad  mov     r14, r9
0x140012cb0  mov     r15, [rsp+198h+arg_20]
0x140012cb8  mov     rsi, rdx
0x140012cbb  mov     r13, [rsp+198h+arg_28]
0x140012cc3  mov     rbx, rcx
0x140012cc6  mov     rdi, [r9]
0x140012cc9  movzx   r12d, r8b
0x140012ccd  mov     ebp, r12d
0x140012cd0  mov     [rsp+198h+var_168], rdx
0x140012cd5  jz      short loc_140012D1A
0x140012cd7  lea     r9, aBatchRecvUUdpD; "Batch Recv %u UDP datagrams"
0x140012cde  mov     [rsp+198h+var_178], r12d
0x140012ce3  mov     edx, 80h; SizeInBytes
0x140012ce8  lea     rcx, [rsp+198h+DstBuf]; DstBuf
0x140012cf0  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140012cf7  call    cs:__imp__snprintf_s
0x140012cfe  nop     dword ptr [rax+rax+00h]
0x140012d03  lea     r9, [rsp+198h+DstBuf]
0x140012d0b  mov     r8, rbx
0x140012d0e  lea     rdx, QuicConnLogVerbose
0x140012d15  call    McTemplateU0ps_EtwWriteTransfer
0x140012d1a  movsxd  rax, dword ptr [rdi+58h]
0x140012d1e  mov     rcx, [rbx+rax*8+0B38h]
0x140012d26  test    rcx, rcx
0x140012d29  jnz     short loc_140012D42
0x140012d2b  lea     r8, aKeyNoLongerAcc; "Key no longer accepted (batch)"
0x140012d32  mov     rdx, rdi
0x140012d35  mov     rcx, rbx
0x140012d38  call    QuicPacketLogDrop
0x140012d3d  jmp     loc_140012EE1
0x140012d42  test    byte ptr [rdi+5Ch], 40h
0x140012d46  jz      short loc_140012D81
0x140012d48  test    byte ptr [rbx+0F9h], 8
0x140012d4f  jz      short loc_140012D81
0x140012d51  mov     rcx, [rcx+10h]
0x140012d55  lea     r9, [rsp+198h+var_158]
0x140012d5a  mov     r8, r15
0x140012d5d  movzx   edx, r12b
0x140012d61  call    CxPlatHpComputeMask
0x140012d66  test    eax, eax
0x140012d68  jns     short loc_140012D93
0x140012d6a  lea     r8, aFailedToComput; "Failed to compute HP mask"
0x140012d71  mov     rdx, rdi
0x140012d74  mov     rcx, rbx
0x140012d77  call    QuicPacketLogDrop
0x140012d7c  jmp     loc_140012EE1
0x140012d81  shl     ebp, 4
0x140012d84  lea     rcx, [rsp+198h+var_158]; void *
0x140012d89  mov     r8d, ebp; Size
0x140012d8c  xor     edx, edx; Val
0x140012d8e  call    memset
0x140012d93  test    r12b, r12b
0x140012d96  jz      loc_140012EE1
0x140012d9c  lea     r15, [rsp+198h+var_158]
0x140012da1  nop     dword ptr [rax+00h]
0x140012da5  nop     word ptr [rax+rax+00000000h]
0x140012db0  mov     rdi, [r14]
0x140012db3  mov     r8, r15
0x140012db6  mov     rdx, rdi
0x140012db9  mov     rcx, rbx
0x140012dbc  movzx   ebp, byte ptr [rdi+1Ch]
0x140012dc0  and     ebp, 3
0x140012dc3  call    QuicConnRecvPrepareDecrypt
0x140012dc8  test    al, al
0x140012dca  jz      loc_140012EAA
0x140012dd0  mov     r8, rdi
0x140012dd3  mov     rdx, rsi
0x140012dd6  mov     rcx, rbx
0x140012dd9  call    QuicConnRecvDecryptAndAuthenticate
0x140012dde  test    al, al
0x140012de0  jz      loc_140012EAA
0x140012de6  mov     r9d, ebp
0x140012de9  mov     r8, rdi
0x140012dec  mov     rdx, rsi
0x140012def  mov     rcx, rbx
0x140012df2  call    QuicConnRecvFrames
0x140012df7  test    al, al
0x140012df9  jz      loc_140012ECF
0x140012dff  mov     r8, rdi
0x140012e02  lea     rdx, [rsp+198h+var_168]
0x140012e07  mov     rcx, rbx
0x140012e0a  call    QuicConnRecvPostProcessing
0x140012e0f  movzx   eax, byte ptr [rdi+5Dh]
0x140012e13  mov     rsi, [rsp+198h+var_168]
0x140012e18  shr     al, 1
0x140012e1a  and     al, 1
0x140012e1c  or      [r13+0], al
0x140012e20  mov     rax, [rbx+50h]
0x140012e24  test    rax, rax
0x140012e27  jz      short loc_140012E6A
0x140012e29  test    byte ptr [rax+10h], 2
0x140012e2d  jnz     short loc_140012E6A
0x140012e2f  test    byte ptr [rsi+1], 2
0x140012e33  jz      short loc_140012E6A
0x140012e35  test    byte ptr [rsi+2], 4
0x140012e39  jnz     short loc_140012E6A
0x140012e3b  test    byte ptr [rdi+5Dh], 2
0x140012e3f  jz      short loc_140012E6A
0x140012e41  mov     rax, [r14]
0x140012e44  xor     edx, edx
0x140012e46  movzx   ecx, cs:word_14005C55C
0x140012e4d  movzx   eax, word ptr [rax+1Ah]
0x140012e51  div     ecx
0x140012e53  movzx   eax, word ptr [r13+2]
0x140012e58  cmp     edx, eax
0x140012e5a  jz      short loc_140012E6A
0x140012e5c  mov     [r13+2], dx
0x140012e61  mov     byte ptr [r13+1], 1
0x140012e66  or      byte ptr [rsi+2], 4
0x140012e6a  test    byte ptr [rdi+5Ch], 4
0x140012e6e  jz      short loc_140012ECF
0x140012e70  test    byte ptr [rdi+5Dh], 4
0x140012e74  jz      short loc_140012ECF
0x140012e76  cmp     dword ptr [rbx], 4
0x140012e79  mov     rax, [rdi+38h]
0x140012e7d  movzx   eax, byte ptr [rax]
0x140012e80  jnz     short loc_140012E95
0x140012e82  movzx   ecx, byte ptr [rsi+1]
0x140012e86  and     al, 0E0h
0x140012e88  shl     al, 2
0x140012e8b  and     cl, 7Fh
0x140012e8e  or      al, cl
0x140012e90  mov     [rsi+1], al
0x140012e93  jmp     short loc_140012ECF
0x140012e95  shl     al, 2
0x140012e98  not     al
0x140012e9a  movzx   ecx, al
0x140012e9d  xor     cl, [rsi+1]
0x140012ea0  and     cl, 7Fh
0x140012ea3  xor     cl, al
0x140012ea5  mov     [rsi+1], cl
0x140012ea8  jmp     short loc_140012ECF
0x140012eaa  movzx   ecx, byte ptr [rbx+0FBh]
0x140012eb1  test    cl, 40h
0x140012eb4  jz      short loc_140012ECF
0x140012eb6  test    cl, cl
0x140012eb8  js      short loc_140012ECF
0x140012eba  mov     eax, [rbx+0F2Ch]
0x140012ec0  and     cl, 0BFh
0x140012ec3  mov     [rbx+0FBh], cl
0x140012ec9  mov     [rbx+0E34h], eax
0x140012ecf  add     r15, 10h
0x140012ed3  add     r14, 8
0x140012ed7  sub     r12, 1
0x140012edb  jnz     loc_140012DB0
0x140012ee1  mov     rcx, [rsp+198h+var_58]
0x140012ee9  xor     rcx, rsp; StackCookie
0x140012eec  call    __security_check_cookie
0x140012ef1  add     rsp, 158h
0x140012ef8  pop     r15
0x140012efa  pop     r14
0x140012efc  pop     r13
0x140012efe  pop     r12
0x140012f00  pop     rdi
0x140012f01  pop     rsi
0x140012f02  pop     rbp
0x140012f03  pop     rbx
0x140012f04  retn
```
