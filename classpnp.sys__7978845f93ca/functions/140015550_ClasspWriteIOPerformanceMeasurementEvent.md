# ClasspWriteIOPerformanceMeasurementEvent

- ea: `0x140015550`
- end: `0x140015706`
- name: `ClasspWriteIOPerformanceMeasurementEvent`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001ccb0`

## callees

- `0x140015550`
- `0x14003d954`
- `0x14003da0c`

## pseudocode

```c
void __fastcall ClasspWriteIOPerformanceMeasurementEvent(_QWORD *a1)
{
  __int64 v1; // r10
  _BYTE *v2; // rdx
  __int64 v3; // r9
  char v4; // bl
  __int64 v5; // r15
  char v6; // r11
  char *v7; // r8
  unsigned int v8; // esi
  __int64 v9; // rbp
  unsigned __int64 v10; // rdi
  _BYTE *v11; // r12
  __int64 v12; // r14
  int v13; // edx

  v1 = a1[6];
  v2 = *(_BYTE **)(v1 + 184);
  if ( v2 )
  {
    v3 = a1[36];
    v4 = 0;
    v5 = *(_QWORD *)(a1[5] + 64LL);
    if ( *v2 == 3 || (v6 = 1, *v2 == 4) )
      v6 = 0;
    if ( *(_BYTE *)(v3 + 2) != 40 )
    {
      v7 = (char *)(v3 + 72);
      goto LABEL_13;
    }
    v7 = 0;
    if ( !*(_DWORD *)(v3 + 20) )
    {
      v8 = *(_DWORD *)(v3 + 56);
      if ( v8 )
      {
        v9 = 0;
        do
        {
          v2 = (_BYTE *)*(unsigned int *)(v3 + 4 * v9 + 120);
          if ( (unsigned int)v2 >= 0x80 )
          {
            v10 = *(unsigned int *)(v3 + 16);
            if ( (unsigned int)v2 < (unsigned int)v10 )
            {
              v11 = &v2[v3];
              v12 = (unsigned int)v2;
              v13 = *(_DWORD *)&v2[v3];
              if ( v13 == 64 )
              {
                LODWORD(v2) = v12 + 40;
                if ( v12 + 40 <= v10 )
                {
                  if ( !v11[10] )
                    break;
                  goto LABEL_26;
                }
              }
              else
              {
                LODWORD(v2) = v13 - 65;
                if ( (_DWORD)v2 )
                {
                  if ( (_DWORD)v2 == 1 )
                  {
                    LODWORD(v2) = v12 + 40;
                    if ( v12 + 40 <= v10 )
                    {
                      if ( *((_DWORD *)v11 + 3) )
                        v7 = v11 + 32;
                      break;
                    }
                  }
                }
                else
                {
                  LODWORD(v2) = v12 + 56;
                  if ( v12 + 56 <= v10 )
                  {
                    if ( !v11[10] )
                      break;
LABEL_26:
                    v7 = v11 + 24;
                    break;
                  }
                }
              }
            }
          }
          v9 = (unsigned int)(v9 + 1);
        }
        while ( (unsigned int)v9 < v8 );
      }
    }
LABEL_13:
    if ( v7 )
      v4 = *v7;
    if ( v6 )
    {
      if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.CurrentIrp & 4) != 0 )
      {
        if ( v7 )
          LODWORD(v2) = (unsigned __int8)v7[1];
        else
          LOBYTE(v2) = 0;
        McTemplateK0qxpuuup_EtwWriteTransfer(
          (_DWORD)a1,
          (_DWORD)v2,
          (_DWORD)a1 + 328,
          *(_DWORD *)(v5 + 588),
          a1[46],
          a1[4],
          v4,
          (char)v2,
          *(_BYTE *)(v3 + 3),
          v1);
      }
    }
    else if ( SLOBYTE(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) < 0 )
    {
      McTemplateK0qxpuup_EtwWriteTransfer(
        (_DWORD)a1,
        (_DWORD)v2,
        (_DWORD)a1 + 328,
        *(_DWORD *)(v5 + 588),
        a1[46],
        a1[4],
        v4,
        *(_BYTE *)(v3 + 3),
        v1);
    }
  }
}

```

## disassembly

```asm
0x140015550  sub     rsp, 68h
0x140015554  mov     r10, [rcx+30h]
0x140015558  mov     rdx, [r10+0B8h]
0x14001555f  test    rdx, rdx
0x140015562  jz      loc_14001564E
0x140015568  mov     rax, [rcx+28h]
0x14001556c  mov     r9, [rcx+120h]
0x140015573  mov     [rsp+68h+arg_0], rbx
0x140015578  xor     bl, bl
0x14001557a  mov     [rsp+68h+var_18], r15
0x14001557f  mov     r15, [rax+40h]
0x140015583  movzx   eax, byte ptr [rdx]
0x140015586  cmp     al, 3
0x140015588  jz      loc_140015689
0x14001558e  mov     r11b, 1
0x140015591  cmp     al, 4
0x140015593  jz      loc_140015689
0x140015599  cmp     byte ptr [r9+2], 28h ; '('
0x14001559e  jnz     loc_140015654
0x1400155a4  xor     r8d, r8d
0x1400155a7  cmp     [r9+14h], r8d
0x1400155ab  jnz     short loc_140015629
0x1400155ad  mov     [rsp+68h+arg_10], rsi
0x1400155b5  mov     esi, [r9+38h]
0x1400155b9  test    esi, esi
0x1400155bb  jz      short loc_140015621
0x1400155bd  mov     [rsp+68h+arg_8], rbp
0x1400155c2  xor     ebp, ebp
0x1400155c4  mov     [rsp+68h+arg_18], rdi
0x1400155cc  mov     [rsp+68h+var_8], r12
0x1400155d1  mov     [rsp+68h+var_10], r14
0x1400155d6  mov     edx, [r9+rbp*4+78h]
0x1400155db  cmp     edx, 80h
0x1400155e1  jb      short loc_140015604
0x1400155e3  mov     edi, [r9+10h]
0x1400155e7  cmp     edx, edi
0x1400155e9  jnb     short loc_140015604
0x1400155eb  lea     r12, [rdx+r9]
0x1400155ef  mov     r14d, edx
0x1400155f2  mov     edx, [r12]
0x1400155f6  cmp     edx, 40h ; '@'
0x1400155f9  jnz     short loc_14001565A
0x1400155fb  lea     rdx, [r14+28h]
0x1400155ff  cmp     rdx, rdi
0x140015602  jbe     short loc_14001567B
0x140015604  inc     ebp
0x140015606  cmp     ebp, esi
0x140015608  jb      short loc_1400155D6
0x14001560a  mov     r14, [rsp+68h+var_10]
0x14001560f  mov     r12, [rsp+68h+var_8]
0x140015614  mov     rdi, [rsp+68h+arg_18]
0x14001561c  mov     rbp, [rsp+68h+arg_8]
0x140015621  mov     rsi, [rsp+68h+arg_10]
0x140015629  test    r8, r8
0x14001562c  jz      short loc_140015632
0x14001562e  movzx   ebx, byte ptr [r8]
0x140015632  test    r11b, r11b
0x140015635  jnz     short loc_1400156AB
0x140015637  cmp     byte ptr cs:WPP_MAIN_CB.Queue+38h, r11b
0x14001563e  jl      loc_1400156C7
0x140015644  mov     rbx, [rsp+68h+arg_0]
0x140015649  mov     r15, [rsp+68h+var_18]
0x14001564e  add     rsp, 68h
0x140015652  retn
0x140015654  lea     r8, [r9+48h]
0x140015658  jmp     short loc_140015629
0x14001565a  sub     edx, 41h ; 'A'
0x14001565d  jz      short loc_140015691
0x14001565f  cmp     edx, 1
0x140015662  jnz     short loc_140015604
0x140015664  lea     rdx, [r14+28h]
0x140015668  cmp     rdx, rdi
0x14001566b  ja      short loc_140015604
0x14001566d  cmp     [r12+0Ch], r8d
0x140015672  jbe     short loc_14001560A
0x140015674  lea     r8, [r12+20h]
0x140015679  jmp     short loc_14001560A
0x14001567b  cmp     [r12+0Ah], bl
0x140015680  jbe     short loc_14001560A
0x140015682  lea     r8, [r12+18h]
0x140015687  jmp     short loc_14001560A
0x140015689  xor     r11b, r11b
0x14001568c  jmp     loc_140015599
0x140015691  lea     rdx, [r14+38h]
0x140015695  cmp     rdx, rdi
0x140015698  ja      loc_140015604
0x14001569e  cmp     [r12+0Ah], bl
0x1400156a3  jbe     loc_14001560A
0x1400156a9  jmp     short loc_140015682
0x1400156ab  test    byte ptr cs:WPP_MAIN_CB.Queue+38h, 4
0x1400156b2  jz      short loc_140015644
0x1400156b4  test    r8, r8
0x1400156b7  jz      loc_140040964
0x1400156bd  movzx   edx, byte ptr [r8+1]
0x1400156c2  jmp     loc_140040966
0x1400156c7  movzx   eax, byte ptr [r9+3]
0x1400156cc  lea     r8, [rcx+148h]
0x1400156d3  mov     r9d, [r15+24Ch]
0x1400156da  mov     [rsp+68h+var_28], r10
0x1400156df  mov     [rsp+68h+var_30], al
0x1400156e3  mov     rax, [rcx+20h]
0x1400156e7  mov     [rsp+68h+var_38], bl
0x1400156eb  mov     [rsp+68h+var_40], rax
0x1400156f0  mov     rax, [rcx+170h]
0x1400156f7  mov     [rsp+68h+var_48], rax
0x1400156fc  call    McTemplateK0qxpuup_EtwWriteTransfer
0x140015701  jmp     loc_140015644
0x140040964  xor     dl, dl
0x140040966  movzx   eax, byte ptr [r9+3]
0x14004096b  lea     r8, [rcx+148h]
0x140040972  mov     r9d, [r15+24Ch]
0x140040979  mov     [rsp+68h+var_20], r10
0x14004097e  mov     byte ptr [rsp+68h+var_28], al
0x140040982  mov     rax, [rcx+20h]
0x140040986  mov     [rsp+68h+var_30], dl
0x14004098a  mov     [rsp+68h+var_38], bl
0x14004098e  mov     [rsp+68h+var_40], rax
0x140040993  mov     rax, [rcx+170h]
0x14004099a  mov     [rsp+68h+var_48], rax
0x14004099f  call    McTemplateK0qxpuuup_EtwWriteTransfer
0x1400409a4  nop
0x1400409a5  jmp     loc_140015644
```
