# RetrieveTag

- ea: `0x140014370`
- end: `0x1400145d7`
- name: `RetrieveTag`
- size: `615`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400119ec`
- `0x140011e48`
- `0x140013c04`
- `0x140014164`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x140014370`

## pseudocode

```c
__int64 __fastcall RetrieveTag(
        __int64 a1,
        int a2,
        unsigned __int16 *a3,
        __int64 *a4,
        unsigned __int16 a5,
        __int64 a6,
        unsigned int a7,
        char a8)
{
  __int64 result; // rax
  PDEVICE_OBJECT v13; // rcx
  unsigned __int16 v14; // dx
  __int16 *v15; // rsi
  unsigned __int64 v16; // rcx
  __int16 v17; // ax
  __int16 v18; // bp
  _WORD *v19; // rsi
  unsigned __int16 v20; // bp
  int v21; // edi
  int v22; // edi
  int v23; // edi
  int v24; // edi
  int v25; // edi
  int v26; // edi
  int v27; // edi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
  }
  *a3 = 0;
  *a4 = 0;
  result = *(_QWORD *)(a1 + 112);
  if ( *(_BYTE *)(result + 15) )
  {
    if ( a6 )
      v15 = (__int16 *)(a6 + a5);
    else
      v15 = *(__int16 **)(a1 + 120);
    v16 = (unsigned __int64)v15 + a7;
    while ( 1 )
    {
      result = (__int64)(v15 + 2);
      if ( (unsigned __int64)(v15 + 2) > v16 )
        break;
      v17 = *v15;
      v18 = v15[1];
      v19 = v15 + 2;
      result = (unsigned __int16)__ROR2__(v17, 8);
      v20 = __ROR2__(v18, 8);
      if ( (unsigned __int16)result == a2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          result = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (result & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            result = WPP_SF_d(
                       (__int64)WPP_GLOBAL_Control->AttachedDevice,
                       0xCu,
                       (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids,
                       0);
        }
        *a3 = v20;
        *a4 = (__int64)v19;
        if ( v19 && a8 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            result = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( (result & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              result = WPP_SF_(
                         (__int64)WPP_GLOBAL_Control->AttachedDevice,
                         0xDu,
                         (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
          }
          v21 = a2 - 257;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              v23 = v22 - 1;
              if ( v23 )
              {
                v24 = v23 - 1;
                if ( v24 )
                {
                  v25 = v24 - 12;
                  if ( v25 )
                  {
                    v26 = v25 - 241;
                    if ( v26 )
                    {
                      v27 = v26 - 1;
                      if ( v27 )
                      {
                        if ( v27 != 2 )
                          break;
                        *(_DWORD *)(a1 + 96) = 516;
                      }
                      else
                      {
                        *(_DWORD *)(a1 + 96) = 514;
                      }
                    }
                    else
                    {
                      *(_DWORD *)(a1 + 96) = 513;
                    }
                    *(_WORD *)(a1 + 100) = *a3;
                    result = *a4;
                    *(_QWORD *)(a1 + 104) = *a4;
                  }
                  else
                  {
                    *(_WORD *)(a1 + 80) = *a3;
                    result = *a4;
                    *(_QWORD *)(a1 + 88) = *a4;
                  }
                }
                else
                {
                  *(_WORD *)(a1 + 64) = *a3;
                  result = *a4;
                  *(_QWORD *)(a1 + 72) = *a4;
                }
              }
              else
              {
                *(_WORD *)(a1 + 48) = *a3;
                result = *a4;
                *(_QWORD *)(a1 + 56) = *a4;
              }
            }
            else
            {
              *(_WORD *)(a1 + 32) = *a3;
              result = *a4;
              *(_QWORD *)(a1 + 40) = *a4;
            }
          }
          else
          {
            *(_WORD *)(a1 + 16) = *a3;
            result = *a4;
            *(_QWORD *)(a1 + 24) = *a4;
          }
        }
        break;
      }
      v15 = (_WORD *)((char *)v19 + v20);
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v14 = 14;
        return WPP_SF_((__int64)v13->AttachedDevice, v14, (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
      }
    }
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v14 = 11;
        return WPP_SF_((__int64)v13->AttachedDevice, v14, (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140014370  push    rbx
0x140014372  push    rbp
0x140014373  push    rsi
0x140014374  push    rdi
0x140014375  push    r14
0x140014377  push    r15
0x140014379  sub     rsp, 28h
0x14001437d  mov     r14, r9
0x140014380  mov     r15, r8
0x140014383  mov     edi, edx
0x140014385  mov     rbx, rcx
0x140014388  mov     rcx, cs:WPP_GLOBAL_Control
0x14001438f  lea     r8, WPP_GLOBAL_Control
0x140014396  cmp     rcx, r8
0x140014399  jz      short loc_1400143C4
0x14001439b  mov     eax, [rcx+2Ch]
0x14001439e  test    al, 20h
0x1400143a0  jz      short loc_1400143C4
0x1400143a2  cmp     byte ptr [rcx+29h], 4
0x1400143a6  jb      short loc_1400143C4
0x1400143a8  mov     rcx, [rcx+18h]
0x1400143ac  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x1400143b3  mov     edx, 0Ah
0x1400143b8  call    WPP_SF_
0x1400143bd  lea     r8, WPP_GLOBAL_Control
0x1400143c4  xor     eax, eax
0x1400143c6  mov     [r15], ax
0x1400143ca  mov     [r14], rax
0x1400143cd  mov     rax, [rbx+70h]
0x1400143d1  cmp     byte ptr [rax+0Fh], 0
0x1400143d5  jnz     short loc_140014406
0x1400143d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400143de  cmp     rcx, r8
0x1400143e1  jz      loc_1400145C9
0x1400143e7  mov     eax, [rcx+2Ch]
0x1400143ea  test    al, 20h
0x1400143ec  jz      loc_1400145C9
0x1400143f2  cmp     byte ptr [rcx+29h], 4
0x1400143f6  jb      loc_1400145C9
0x1400143fc  mov     edx, 0Bh
0x140014401  jmp     loc_1400145B9
0x140014406  mov     rax, [rsp+58h+arg_28]
0x14001440e  mov     ecx, [rsp+58h+arg_30]
0x140014415  test    rax, rax
0x140014418  jz      short loc_140014427
0x14001441a  movzx   esi, [rsp+58h+arg_20]
0x140014422  add     rsi, rax
0x140014425  jmp     short loc_14001442B
0x140014427  mov     rsi, [rbx+78h]
0x14001442b  add     rcx, rsi
0x14001442e  jmp     short loc_140014453
0x140014430  movzx   eax, word ptr [rsi]
0x140014433  movzx   ebp, word ptr [rsi+2]
0x140014437  add     rsi, 4
0x14001443b  ror     ax, 8
0x14001443f  mov     rdx, rsi
0x140014442  movzx   eax, ax
0x140014445  ror     bp, 8
0x140014449  cmp     eax, edi
0x14001444b  jz      short loc_140014461
0x14001444d  movzx   esi, bp
0x140014450  add     rsi, rdx
0x140014453  lea     rax, [rsi+4]
0x140014457  cmp     rax, rcx
0x14001445a  jbe     short loc_140014430
0x14001445c  jmp     loc_14001459B
0x140014461  mov     rcx, cs:WPP_GLOBAL_Control
0x140014468  cmp     rcx, r8
0x14001446b  jz      short loc_140014499
0x14001446d  mov     eax, [rcx+2Ch]
0x140014470  test    al, 20h
0x140014472  jz      short loc_140014499
0x140014474  cmp     byte ptr [rcx+29h], 3
0x140014478  jb      short loc_140014499
0x14001447a  mov     rcx, [rcx+18h]
0x14001447e  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x140014485  mov     edx, 0Ch
0x14001448a  xor     r9d, r9d
0x14001448d  call    WPP_SF_d
0x140014492  lea     r8, WPP_GLOBAL_Control
0x140014499  mov     [r15], bp
0x14001449d  mov     [r14], rsi
0x1400144a0  test    rsi, rsi
0x1400144a3  jz      loc_14001459B
0x1400144a9  cmp     [rsp+58h+arg_38], 0
0x1400144b1  jz      loc_14001459B
0x1400144b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400144be  cmp     rcx, r8
0x1400144c1  jz      short loc_1400144EC
0x1400144c3  mov     eax, [rcx+2Ch]
0x1400144c6  test    al, 20h
0x1400144c8  jz      short loc_1400144EC
0x1400144ca  cmp     byte ptr [rcx+29h], 4
0x1400144ce  jb      short loc_1400144EC
0x1400144d0  mov     rcx, [rcx+18h]
0x1400144d4  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x1400144db  mov     edx, 0Dh
0x1400144e0  call    WPP_SF_
0x1400144e5  lea     r8, WPP_GLOBAL_Control
0x1400144ec  sub     edi, 101h
0x1400144f2  jz      loc_14001458C
0x1400144f8  sub     edi, 1
0x1400144fb  jz      short loc_14001457B
0x1400144fd  sub     edi, 1
0x140014500  jz      short loc_14001456A
0x140014502  sub     edi, 1
0x140014505  jz      short loc_140014559
0x140014507  sub     edi, 0Ch
0x14001450a  jz      short loc_140014548
0x14001450c  sub     edi, 0F1h
0x140014512  jz      short loc_140014530
0x140014514  sub     edi, 1
0x140014517  jz      short loc_140014527
0x140014519  cmp     edi, 2
0x14001451c  jnz     short loc_14001459B
0x14001451e  mov     dword ptr [rbx+60h], 204h
0x140014525  jmp     short loc_140014537
0x140014527  mov     dword ptr [rbx+60h], 202h
0x14001452e  jmp     short loc_140014537
0x140014530  mov     dword ptr [rbx+60h], 201h
0x140014537  movzx   eax, word ptr [r15]
0x14001453b  mov     [rbx+64h], ax
0x14001453f  mov     rax, [r14]
0x140014542  mov     [rbx+68h], rax
0x140014546  jmp     short loc_14001459B
0x140014548  movzx   eax, word ptr [r15]
0x14001454c  mov     [rbx+50h], ax
0x140014550  mov     rax, [r14]
0x140014553  mov     [rbx+58h], rax
0x140014557  jmp     short loc_14001459B
0x140014559  movzx   eax, word ptr [r15]
0x14001455d  mov     [rbx+40h], ax
0x140014561  mov     rax, [r14]
0x140014564  mov     [rbx+48h], rax
0x140014568  jmp     short loc_14001459B
0x14001456a  movzx   eax, word ptr [r15]
0x14001456e  mov     [rbx+30h], ax
0x140014572  mov     rax, [r14]
0x140014575  mov     [rbx+38h], rax
0x140014579  jmp     short loc_14001459B
0x14001457b  movzx   eax, word ptr [r15]
0x14001457f  mov     [rbx+20h], ax
0x140014583  mov     rax, [r14]
0x140014586  mov     [rbx+28h], rax
0x14001458a  jmp     short loc_14001459B
0x14001458c  movzx   eax, word ptr [r15]
0x140014590  mov     [rbx+10h], ax
0x140014594  mov     rax, [r14]
0x140014597  mov     [rbx+18h], rax
0x14001459b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400145a2  cmp     rcx, r8
0x1400145a5  jz      short loc_1400145C9
0x1400145a7  mov     eax, [rcx+2Ch]
0x1400145aa  test    al, 20h
0x1400145ac  jz      short loc_1400145C9
0x1400145ae  cmp     byte ptr [rcx+29h], 4
0x1400145b2  jb      short loc_1400145C9
0x1400145b4  mov     edx, 0Eh
0x1400145b9  mov     rcx, [rcx+18h]
0x1400145bd  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x1400145c4  call    WPP_SF_
0x1400145c9  add     rsp, 28h
0x1400145cd  pop     r15
0x1400145cf  pop     r14
0x1400145d1  pop     rdi
0x1400145d2  pop     rsi
0x1400145d3  pop     rbp
0x1400145d4  pop     rbx
0x1400145d5  retn
```
