# QuicSendPathChallenges

- ea: `0x140049050`
- end: `0x140049230`
- name: `QuicSendPathChallenges`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140016210`

## callees

- `0x140017580`
- `0x140022e74`
- `0x140030044`
- `0x14003c8e0`
- `0x14003ce00`
- `0x1400489b0`
- `0x140049050`
- `0x140049c74`
- `0x140049cc8`
- `0x140049e18`

## pseudocode

```c
__int64 __fastcall QuicSendPathChallenges(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rdi
  unsigned __int8 i; // si
  __int64 v5; // rcx
  __int64 v6; // r14
  __int64 v7; // r10
  __int64 v8; // rbx
  int v9; // r9d
  __int64 v10; // [rsp+28h] [rbp-E0h]
  __int64 v11; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v12[100]; // [rsp+48h] [rbp-C0h] BYREF
  _UNKNOWN *retaddr; // [rsp+390h] [rbp+288h] BYREF

  result = (__int64)&retaddr;
  v2 = a1 - 3416;
  for ( i = 0; i < *(_BYTE *)(v2 + 275); ++i )
  {
    result = i;
    v5 = 240LL * i;
    v6 = v5 + v2 + 320;
    if ( (*(_BYTE *)(v5 + v2 + 322) & 1) != 0 && *(_DWORD *)(v5 + v2 + 528) >= 0x4Cu )
    {
      result = CxPlatIsRouteReady(v2, v5 + v2 + 320);
      if ( (_BYTE)result )
      {
        memset(v12, 0, sizeof(v12));
        result = QuicPacketBuilderInitialize(v12, v2, v6);
        if ( (_BYTE)result )
        {
          result = QuicPacketBuilderPrepareForControlFrames(v12, 0, 1024);
          if ( (_BYTE)result )
          {
            v7 = v12[4];
            if ( (*(_BYTE *)(v6 + 1) & 0x40) == 0 )
            {
              LOWORD(v12[48]) = MaxUdpPayloadSizeForFamily(
                                  *(unsigned __int16 *)(v12[1] + 56LL),
                                  *(unsigned __int16 *)(v12[1] + 16LL));
              if ( (unsigned int)LOWORD(v12[48]) > *(_DWORD *)v7 )
                LOWORD(v12[48]) = *(_WORD *)v7;
            }
            v8 = *(_QWORD *)(v6 + 220);
            v9 = (unsigned __int16)(*(_WORD *)v7 - BYTE2(v12[46]));
            v10 = *(_QWORD *)(v7 + 8);
            v11 = v8;
            if ( (unsigned __int8)QuicPathChallengeFrameEncode(
                                    26,
                                    (unsigned int)&v11,
                                    (unsigned int)&v12[47] + 2,
                                    v9,
                                    v10) )
            {
              *(_QWORD *)(v12[51] + 96LL) = v8;
              *(_WORD *)(v12[51] + 24LL * *(unsigned __int8 *)(v12[51] + 90LL) + 114) = 26;
              *(_BYTE *)(v12[51] + 88LL) |= 4u;
              ++*(_BYTE *)(v12[51] + 90LL);
              *(_BYTE *)(v6 + 2) &= ~1u;
            }
            QuicPacketBuilderFinalize((unsigned __int64)v12, 1);
            result = QuicPacketBuilderCleanup(v12);
          }
        }
      }
      else
      {
        *(_DWORD *)(a1 + 72) |= 0x400u;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140049050  mov     rax, rsp
0x140049053  mov     [rax+10h], rbx
0x140049057  mov     [rax+18h], rsi
0x14004905b  mov     [rax+20h], rdi
0x14004905f  push    rbp
0x140049060  push    r14
0x140049062  push    r15
0x140049064  lea     rbp, [rax-288h]
0x14004906b  sub     rsp, 370h
0x140049072  mov     rax, cs:__security_cookie
0x140049079  xor     rax, rsp
0x14004907c  mov     [rbp+280h+var_20], rax
0x140049083  lea     rdi, [rcx-0D58h]
0x14004908a  xor     sil, sil
0x14004908d  mov     r15, rcx
0x140049090  cmp     [rdi+113h], sil
0x140049097  jbe     loc_140049203
0x14004909d  movzx   eax, sil
0x1400490a1  lea     r14, [rdi+140h]
0x1400490a8  imul    rcx, rax, 0F0h
0x1400490af  add     r14, rcx
0x1400490b2  test    byte ptr [rcx+rdi+142h], 1
0x1400490ba  jz      loc_1400491F3
0x1400490c0  cmp     dword ptr [rcx+rdi+210h], 4Ch ; 'L'
0x1400490c8  jb      loc_1400491F3
0x1400490ce  mov     rdx, r14
0x1400490d1  mov     rcx, rdi
0x1400490d4  call    CxPlatIsRouteReady
0x1400490d9  test    al, al
0x1400490db  jnz     short loc_1400490E8
0x1400490dd  bts     dword ptr [r15+48h], 0Ah
0x1400490e3  jmp     loc_1400491F3
0x1400490e8  xor     edx, edx; Val
0x1400490ea  lea     rcx, [rsp+380h+var_340]; void *
0x1400490ef  mov     r8d, 320h; Size
0x1400490f5  call    memset
0x1400490fa  mov     r8, r14
0x1400490fd  lea     rcx, [rsp+380h+var_340]
0x140049102  mov     rdx, rdi
0x140049105  call    QuicPacketBuilderInitialize
0x14004910a  test    al, al
0x14004910c  jz      loc_1400491F3
0x140049112  xor     edx, edx
0x140049114  lea     rcx, [rsp+380h+var_340]
0x140049119  mov     r8d, 400h
0x14004911f  call    QuicPacketBuilderPrepareForControlFrames
0x140049124  test    al, al
0x140049126  jz      loc_1400491F3
0x14004912c  test    byte ptr [r14+1], 40h
0x140049131  mov     r10, [rsp+380h+var_320]
0x140049136  jnz     short loc_140049164
0x140049138  mov     rcx, [rsp+380h+var_338]
0x14004913d  movzx   edx, word ptr [rcx+10h]
0x140049141  movzx   ecx, word ptr [rcx+38h]
0x140049145  call    MaxUdpPayloadSizeForFamily
0x14004914a  movzx   ecx, ax
0x14004914d  mov     [rbp+280h+var_1C0], cx
0x140049154  cmp     ecx, [r10]
0x140049157  jbe     short loc_140049164
0x140049159  movzx   eax, word ptr [r10]
0x14004915d  mov     [rbp+280h+var_1C0], ax
0x140049164  movzx   eax, [rbp+280h+var_1CE]
0x14004916b  lea     r8, [rbp+280h+var_1C6]
0x140049172  movzx   r9d, word ptr [r10]
0x140049176  lea     rdx, [rsp+380h+var_350]
0x14004917b  mov     rbx, [r14+0DCh]
0x140049182  sub     r9w, ax
0x140049186  mov     rax, [r10+8]
0x14004918a  mov     ecx, 1Ah
0x14004918f  mov     [rsp+380h+var_360], rax
0x140049194  mov     [rsp+380h+var_350], rbx
0x140049199  call    QuicPathChallengeFrameEncode
0x14004919e  test    al, al
0x1400491a0  jz      short loc_1400491DD
0x1400491a2  mov     rax, [rbp+280h+var_1A8]
0x1400491a9  mov     [rax+60h], rbx
0x1400491ad  mov     rdx, [rbp+280h+var_1A8]
0x1400491b4  movzx   eax, byte ptr [rdx+5Ah]
0x1400491b8  lea     rcx, [rax+rax*2]
0x1400491bc  mov     word ptr [rdx+rcx*8+72h], 1Ah
0x1400491c3  mov     rax, [rbp+280h+var_1A8]
0x1400491ca  or      byte ptr [rax+58h], 4
0x1400491ce  mov     rax, [rbp+280h+var_1A8]
0x1400491d5  inc     byte ptr [rax+5Ah]
0x1400491d8  and     byte ptr [r14+2], 0FEh
0x1400491dd  mov     dl, 1
0x1400491df  lea     rcx, [rsp+380h+var_340]
0x1400491e4  call    QuicPacketBuilderFinalize
0x1400491e9  lea     rcx, [rsp+380h+var_340]
0x1400491ee  call    QuicPacketBuilderCleanup
0x1400491f3  inc     sil
0x1400491f6  cmp     sil, [rdi+113h]
0x1400491fd  jb      loc_14004909D
0x140049203  mov     rcx, [rbp+280h+var_20]
0x14004920a  xor     rcx, rsp; StackCookie
0x14004920d  call    __security_check_cookie
0x140049212  lea     r11, [rsp+380h+var_10]
0x14004921a  mov     rbx, [r11+28h]
0x14004921e  mov     rsi, [r11+30h]
0x140049222  mov     rdi, [r11+38h]
0x140049226  mov     rsp, r11
0x140049229  pop     r15
0x14004922b  pop     r14
0x14004922d  pop     rbp
0x14004922e  retn
```
