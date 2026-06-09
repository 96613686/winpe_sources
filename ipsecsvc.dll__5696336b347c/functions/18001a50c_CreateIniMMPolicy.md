# CreateIniMMPolicy

- ea: `0x18001a50c`
- end: `0x18001a65d`
- name: `CreateIniMMPolicy`
- size: `337`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180019f08`

## callees

- `0x180006f00`
- `0x18000c828`
- `0x18000e510`
- `0x18001a32c`
- `0x18001a50c`
- `0x18001ad54`

## pseudocode

```c
__int64 __fastcall CreateIniMMPolicy(__int64 a1, _QWORD *a2)
{
  _OWORD *v4; // rax
  _OWORD *v5; // rbx
  __int64 v6; // r9
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 result; // rax

  v4 = (_OWORD *)IpsecAllocMem(72);
  v5 = v4;
  if ( !v4 )
  {
    v6 = 8;
    v7 = 8;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
LABEL_20:
      *a2 = 0;
      return v7;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_15;
    v9 = 29;
    goto LABEL_14;
  }
  *v4 = *(_OWORD *)a1;
  v10 = IpsecAllocStr(*(unsigned __int16 **)(a1 + 16));
  *((_QWORD *)v5 + 2) = v10;
  if ( !v10 )
  {
    v6 = 8;
    v7 = 8;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_15;
      v9 = 30;
      goto LABEL_14;
    }
    goto LABEL_19;
  }
  *((_QWORD *)v5 + 3) = 0;
  *((_DWORD *)v5 + 8) = *(_DWORD *)(a1 + 24);
  *((_DWORD *)v5 + 9) = *(_DWORD *)(a1 + 28);
  *((_QWORD *)v5 + 8) = 0;
  result = CreateIniMMOffers(*(_DWORD *)(a1 + 32), *(_QWORD *)(a1 + 40), (unsigned int *)v5 + 10, (__int64 *)v5 + 6);
  v7 = result;
  if ( (_DWORD)result != 13024 && (_DWORD)result )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_15;
      v9 = 31;
      v6 = (unsigned int)result;
LABEL_14:
      WPP_SF_d(v8[2], v9, WPP_3b22585727a234aeebb3c3c9670a017a_Traceguids, v6);
      v8 = WPP_GLOBAL_Control;
LABEL_15:
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
        WPP_SF_d(v8[2], 32, WPP_3b22585727a234aeebb3c3c9670a017a_Traceguids, v7);
      if ( !v5 )
        goto LABEL_20;
    }
LABEL_19:
    FreeIniMMPolicy(v5);
    goto LABEL_20;
  }
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x18001a50c  push    rbx
0x18001a50e  push    rsi
0x18001a50f  push    rdi
0x18001a510  push    r14
0x18001a512  sub     rsp, 28h
0x18001a516  mov     rdi, rcx
0x18001a519  mov     r14, rdx
0x18001a51c  mov     ecx, 48h ; 'H'
0x18001a521  call    IpsecAllocMem
0x18001a526  mov     rbx, rax
0x18001a529  test    rax, rax
0x18001a52c  jnz     short loc_18001A55E
0x18001a52e  lea     r9d, [rax+8]
0x18001a532  mov     edi, r9d
0x18001a535  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a53c  lea     rsi, WPP_GLOBAL_Control
0x18001a543  cmp     rcx, rsi
0x18001a546  jz      loc_18001A645
0x18001a54c  test    byte ptr [rcx+1Ch], 10h
0x18001a550  jz      loc_18001A615
0x18001a556  lea     edx, [rax+1Dh]
0x18001a559  jmp     loc_18001A5FE
0x18001a55e  movups  xmm0, xmmword ptr [rdi]
0x18001a561  movdqu  xmmword ptr [rax], xmm0
0x18001a565  mov     rcx, [rdi+10h]; unsigned __int16 *
0x18001a569  call    IpsecAllocStr
0x18001a56e  mov     [rbx+10h], rax
0x18001a572  test    rax, rax
0x18001a575  jnz     short loc_18001A5A0
0x18001a577  lea     r9d, [rax+8]
0x18001a57b  mov     edi, r9d
0x18001a57e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a585  lea     rsi, WPP_GLOBAL_Control
0x18001a58c  cmp     rcx, rsi
0x18001a58f  jz      loc_18001A63D
0x18001a595  test    byte ptr [rcx+1Ch], 10h
0x18001a599  jz      short loc_18001A615
0x18001a59b  lea     edx, [rax+1Eh]
0x18001a59e  jmp     short loc_18001A5FE
0x18001a5a0  mov     qword ptr [rbx+18h], 0
0x18001a5a8  lea     r9, [rbx+30h]
0x18001a5ac  mov     eax, [rdi+18h]
0x18001a5af  lea     r8, [rbx+28h]
0x18001a5b3  mov     [rbx+20h], eax
0x18001a5b6  mov     eax, [rdi+1Ch]
0x18001a5b9  mov     [rbx+24h], eax
0x18001a5bc  mov     qword ptr [rbx+40h], 0
0x18001a5c4  mov     rdx, [rdi+28h]
0x18001a5c8  mov     ecx, [rdi+20h]
0x18001a5cb  call    CreateIniMMOffers
0x18001a5d0  mov     edi, eax
0x18001a5d2  cmp     eax, 32E0h
0x18001a5d7  jz      short loc_18001A650
0x18001a5d9  test    eax, eax
0x18001a5db  jz      short loc_18001A650
0x18001a5dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5e4  lea     rsi, WPP_GLOBAL_Control
0x18001a5eb  cmp     rcx, rsi
0x18001a5ee  jz      short loc_18001A63D
0x18001a5f0  test    byte ptr [rcx+1Ch], 10h
0x18001a5f4  jz      short loc_18001A615
0x18001a5f6  mov     edx, 1Fh
0x18001a5fb  mov     r9d, eax
0x18001a5fe  mov     rcx, [rcx+10h]
0x18001a602  lea     r8, WPP_3b22585727a234aeebb3c3c9670a017a_Traceguids
0x18001a609  call    WPP_SF_d
0x18001a60e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a615  cmp     rcx, rsi
0x18001a618  jz      short loc_18001A638
0x18001a61a  test    byte ptr [rcx+1Ch], 10h
0x18001a61e  jz      short loc_18001A638
0x18001a620  mov     rcx, [rcx+10h]
0x18001a624  lea     r8, WPP_3b22585727a234aeebb3c3c9670a017a_Traceguids
0x18001a62b  mov     edx, 20h ; ' '
0x18001a630  mov     r9d, edi
0x18001a633  call    WPP_SF_d
0x18001a638  test    rbx, rbx
0x18001a63b  jz      short loc_18001A645
0x18001a63d  mov     rcx, rbx; lpMem
0x18001a640  call    FreeIniMMPolicy
0x18001a645  mov     qword ptr [r14], 0
0x18001a64c  mov     eax, edi
0x18001a64e  jmp     short loc_18001A653
0x18001a650  mov     [r14], rbx
0x18001a653  add     rsp, 28h
0x18001a657  pop     r14
0x18001a659  pop     rdi
0x18001a65a  pop     rsi
0x18001a65b  pop     rbx
0x18001a65c  retn
```
