# DevAuth2_HostSetResponse

- ea: `0x18000409c`
- end: `0x180004279`
- name: `DevAuth2_HostSetResponse`
- size: `477`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000118c`

## callees

- `0x18000409c`
- `0x180004368`
- `0x1800044a8`
- `0x180004594`
- `0x1800047d0`
- `0x18000490c`

## import_xrefs

- `cng!BCryptHashData` at `0x180004247`
- `cng!BCryptHashData` at `0x180004247`

## pseudocode

```c
__int64 __fastcall DevAuth2_HostSetResponse(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v4; // esi
  UCHAR *v5; // rbp
  char v6; // di
  int v7; // ecx
  int v8; // ecx
  __int64 v9; // rcx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  _OWORD *v13; // rdi
  __int64 v14; // rcx
  _OWORD *v15; // rax
  __int128 v16; // xmm1
  __int64 v17; // rcx

  if ( !a1 )
    return 0;
  if ( a2 && a3 >= 5 && (*(_BYTE *)a2 != 0xC1 || *(_WORD *)(a2 + 1) == 256) )
  {
    v4 = a3 - 5;
    if ( a3 - 5 == (unsigned __int16)__ROR2__(*(_WORD *)(a2 + 3), 8) )
    {
      v5 = (UCHAR *)(a2 + 5);
      v6 = 33;
      v7 = *(unsigned __int8 *)(a1 + 1) - 33;
      if ( !v7 )
      {
        v6 = 34;
        goto LABEL_28;
      }
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = (unsigned int)(v8 - 1);
        if ( (_DWORD)v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( !v11 )
            {
              v6 = 38;
              goto LABEL_28;
            }
            v12 = v11 - 1;
            if ( !v12 )
            {
              v6 = 39;
              goto LABEL_28;
            }
            if ( v12 == 1 && ProcessDeviceFinished_0(a1, a2 + 5, v4) )
            {
              *(_BYTE *)a1 = 2;
              goto LABEL_28;
            }
          }
          else if ( (unsigned int)ProcessDeviceKeyExchange(a1, a2 + 5, v4) )
          {
            v6 = 37;
            goto LABEL_28;
          }
        }
        else
        {
          LODWORD(v9) = 35;
          if ( (unsigned int)DevAuth2_ValidateMessageHeader(v9, a2, a2 + 5, v4) )
          {
            v13 = v5 + 4;
            if ( (unsigned int)VerifyDeviceCert(v5 + 4) )
            {
              v14 = 6;
              v15 = (_OWORD *)(a1 + 280);
              do
              {
                *v15 = *v13;
                v15[1] = v13[1];
                v15[2] = v13[2];
                v15[3] = v13[3];
                v15[4] = v13[4];
                v15[5] = v13[5];
                v15[6] = v13[6];
                v16 = v13[7];
                v13 += 8;
                v15[7] = v16;
                v15 += 8;
                --v14;
              }
              while ( v14 );
              v6 = 36;
LABEL_28:
              *(_BYTE *)(a1 + 1) = v6;
              if ( !v4
                || (v17 = *(_QWORD *)(a1 + 1096)) != 0
                && v5
                && BCryptHashData(*(BCRYPT_HASH_HANDLE *)(v17 + 8), v5, v4, 0) >= 0 )
              {
                *(_DWORD *)(a1 + 8) = 0;
                return 1;
              }
            }
          }
        }
      }
      else if ( (unsigned int)ProcessDeviceHello(a1, a2 + 5, v4) )
      {
        v6 = *(_DWORD *)(a1 + 4) != 0 ? 38 : 35;
        goto LABEL_28;
      }
    }
  }
  *(_BYTE *)a1 = 3;
  return 0;
}

```

## disassembly

```asm
0x18000409c  push    rbx
0x18000409e  push    rbp
0x18000409f  push    rsi
0x1800040a0  push    rdi
0x1800040a1  sub     rsp, 28h
0x1800040a5  mov     rbx, rcx
0x1800040a8  test    rcx, rcx
0x1800040ab  jz      loc_18000426D
0x1800040b1  test    rdx, rdx
0x1800040b4  jz      loc_18000426A
0x1800040ba  cmp     r8d, 5
0x1800040be  jb      loc_18000426A
0x1800040c4  cmp     byte ptr [rdx], 0C1h
0x1800040c7  jnz     short loc_1800040D8
0x1800040c9  mov     eax, 100h
0x1800040ce  cmp     [rdx+1], ax
0x1800040d2  jnz     loc_18000426A
0x1800040d8  movzx   eax, word ptr [rdx+3]
0x1800040dc  lea     esi, [r8-5]
0x1800040e0  ror     ax, 8
0x1800040e4  movzx   eax, ax
0x1800040e7  cmp     esi, eax
0x1800040e9  jnz     loc_18000426A
0x1800040ef  movzx   ecx, byte ptr [rcx+1]
0x1800040f3  lea     rbp, [rdx+5]
0x1800040f7  mov     edi, 21h ; '!'
0x1800040fc  sub     ecx, edi
0x1800040fe  jz      loc_18000421E
0x180004104  sub     ecx, 1
0x180004107  jz      loc_1800041FD
0x18000410d  sub     ecx, 1
0x180004110  jz      short loc_180004176
0x180004112  sub     ecx, 1
0x180004115  jz      short loc_180004158
0x180004117  sub     ecx, 1
0x18000411a  jz      short loc_180004150
0x18000411c  sub     ecx, 1
0x18000411f  jz      short loc_180004148
0x180004121  cmp     ecx, 1
0x180004124  jnz     loc_18000426A
0x18000412a  mov     r8d, esi
0x18000412d  mov     rdx, rbp
0x180004130  mov     rcx, rbx
0x180004133  call    _ProcessDeviceFinished_0
0x180004138  test    eax, eax
0x18000413a  jz      loc_18000426A
0x180004140  mov     byte ptr [rbx], 2
0x180004143  jmp     loc_180004221
0x180004148  mov     dil, 27h ; '''
0x18000414b  jmp     loc_180004221
0x180004150  mov     dil, 26h ; '&'
0x180004153  jmp     loc_180004221
0x180004158  mov     r8d, esi
0x18000415b  mov     rdx, rbp
0x18000415e  mov     rcx, rbx
0x180004161  call    _ProcessDeviceKeyExchange
0x180004166  test    eax, eax
0x180004168  jz      loc_18000426A
0x18000416e  mov     dil, 25h ; '%'
0x180004171  jmp     loc_180004221
0x180004176  mov     r9d, esi
0x180004179  mov     r8, rbp
0x18000417c  mov     cl, 23h ; '#'
0x18000417e  call    DevAuth2_ValidateMessageHeader
0x180004183  test    eax, eax
0x180004185  jz      loc_18000426A
0x18000418b  lea     rdi, [rbp+4]
0x18000418f  mov     rcx, rdi
0x180004192  call    _VerifyDeviceCert
0x180004197  test    eax, eax
0x180004199  jz      loc_18000426A
0x18000419f  mov     ecx, 6
0x1800041a4  lea     rax, [rbx+118h]
0x1800041ab  lea     edx, [rcx+7Ah]
0x1800041ae  movups  xmm0, xmmword ptr [rdi]
0x1800041b1  movups  xmmword ptr [rax], xmm0
0x1800041b4  movups  xmm1, xmmword ptr [rdi+10h]
0x1800041b8  movups  xmmword ptr [rax+10h], xmm1
0x1800041bc  movups  xmm0, xmmword ptr [rdi+20h]
0x1800041c0  movups  xmmword ptr [rax+20h], xmm0
0x1800041c4  movups  xmm1, xmmword ptr [rdi+30h]
0x1800041c8  movups  xmmword ptr [rax+30h], xmm1
0x1800041cc  movups  xmm0, xmmword ptr [rdi+40h]
0x1800041d0  movups  xmmword ptr [rax+40h], xmm0
0x1800041d4  movups  xmm1, xmmword ptr [rdi+50h]
0x1800041d8  movups  xmmword ptr [rax+50h], xmm1
0x1800041dc  movups  xmm0, xmmword ptr [rdi+60h]
0x1800041e0  movups  xmmword ptr [rax+60h], xmm0
0x1800041e4  movups  xmm1, xmmword ptr [rdi+70h]
0x1800041e8  add     rdi, rdx
0x1800041eb  movups  xmmword ptr [rax+70h], xmm1
0x1800041ef  add     rax, rdx
0x1800041f2  sub     rcx, 1
0x1800041f6  jnz     short loc_1800041AE
0x1800041f8  mov     dil, 24h ; '$'
0x1800041fb  jmp     short loc_180004221
0x1800041fd  mov     r8d, esi
0x180004200  mov     rdx, rbp
0x180004203  mov     rcx, rbx
0x180004206  call    _ProcessDeviceHello
0x18000420b  test    eax, eax
0x18000420d  jz      short loc_18000426A
0x18000420f  mov     eax, [rbx+4]
0x180004212  neg     eax
0x180004214  sbb     cl, cl
0x180004216  and     cl, 3
0x180004219  lea     edi, [rcx+23h]
0x18000421c  jmp     short loc_180004221
0x18000421e  mov     dil, 22h ; '"'
0x180004221  mov     [rbx+1], dil
0x180004225  test    esi, esi
0x180004227  jz      short loc_18000425C
0x180004229  mov     rcx, [rbx+448h]
0x180004230  test    rcx, rcx
0x180004233  jz      short loc_18000426A
0x180004235  test    rbp, rbp
0x180004238  jz      short loc_18000426A
0x18000423a  mov     rcx, [rcx+8]; hHash
0x18000423e  xor     r9d, r9d; dwFlags
0x180004241  mov     r8d, esi; cbInput
0x180004244  mov     rdx, rbp; pbInput
0x180004247  call    cs:__imp_BCryptHashData
0x18000424e  nop     dword ptr [rax+rax+00h]
0x180004253  not     eax
0x180004255  shr     eax, 1Fh
0x180004258  test    eax, eax
0x18000425a  jz      short loc_18000426A
0x18000425c  mov     dword ptr [rbx+8], 0
0x180004263  mov     eax, 1
0x180004268  jmp     short loc_18000426F
0x18000426a  mov     byte ptr [rbx], 3
0x18000426d  xor     eax, eax
0x18000426f  add     rsp, 28h
0x180004273  pop     rdi
0x180004274  pop     rsi
0x180004275  pop     rbp
0x180004276  pop     rbx
0x180004277  retn
```
