# McGenControlCallbackV2

- ea: `0x140049f70`
- end: `0x14004a0b1`
- name: `McGenControlCallbackV2`
- size: `321`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14003c980`
- `0x14003ce00`
- `0x140049f70`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  ULONG v7; // edi
  unsigned __int8 v8; // r9
  __int64 v9; // rdx
  int v10; // edx
  ULONG *v11; // r10
  ULONG v12; // eax
  int v13; // eax

  v7 = ControlCode;
  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        *(_QWORD *)&Level = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        *((_DWORD *)CallbackContext + 9) = 1;
        if ( *((_WORD *)CallbackContext + 21) )
        {
          do
          {
            v8 = *((_BYTE *)CallbackContext + 40);
            v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * Level);
            LOBYTE(MatchAnyKeyword) = (*(_BYTE *)(Level + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8)
                                   && (!v9
                                    || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
                                    && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3));
            v10 = 1 << (Level & 0x1F);
            v11 = (ULONG *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)Level >> 5));
            v12 = *v11;
            if ( (_BYTE)MatchAnyKeyword )
              *(_QWORD *)&ControlCode = v12 | v10;
            else
              *(_QWORD *)&ControlCode = v12 & ~v10;
            *v11 = ControlCode;
            *(_QWORD *)&Level = (unsigned int)(Level + 1);
          }
          while ( Level < (unsigned int)*((unsigned __int16 *)CallbackContext + 21) );
        }
      }
    }
    else
    {
      v13 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v13 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v13 - 1) / 32 + 1));
    }
    if ( QuicTraceRundownCallback && v7 - 1 <= 1 && CallbackContext == &MICROSOFT_MSQUIC_PROVIDER_Context )
      QuicTraceRundownCallback(&MICROSOFT_MSQUIC_PROVIDER_Context, *(_QWORD *)&ControlCode, Level, MatchAnyKeyword);
  }
}

```

## disassembly

```asm
0x140049f70  mov     [rsp+arg_0], rbx
0x140049f75  mov     [rsp+arg_8], rsi
0x140049f7a  push    rdi
0x140049f7b  sub     rsp, 20h
0x140049f7f  mov     rbx, [rsp+28h+CallbackContext]
0x140049f84  xor     esi, esi
0x140049f86  mov     edi, edx
0x140049f88  test    rbx, rbx
0x140049f8b  jz      loc_14004A0A0
0x140049f91  mov     eax, edx
0x140049f93  test    edx, edx
0x140049f95  jz      loc_14004A042
0x140049f9b  cmp     eax, 1
0x140049f9e  jnz     loc_14004A079
0x140049fa4  mov     rax, [rsp+28h+MatchAllKeyword]
0x140049fa9  mov     [rbx+28h], r8b
0x140049fad  mov     r8d, esi
0x140049fb0  mov     [rbx+18h], rax
0x140049fb4  mov     [rbx+10h], r9
0x140049fb8  mov     [rbx+24h], edx
0x140049fbb  cmp     si, [rbx+2Ah]
0x140049fbf  jnb     loc_14004A079
0x140049fc5  mov     rax, [rbx+38h]
0x140049fc9  mov     r9b, [rbx+28h]
0x140049fcd  mov     ecx, r8d
0x140049fd0  mov     rdx, [rax+rcx*8]
0x140049fd4  mov     rax, [rbx+40h]
0x140049fd8  cmp     [rcx+rax], r9b
0x140049fdc  jbe     short loc_140049FE3
0x140049fde  test    r9b, r9b
0x140049fe1  jnz     short loc_140049FFD
0x140049fe3  test    rdx, rdx
0x140049fe6  jz      short loc_14004A002
0x140049fe8  test    [rbx+10h], rdx
0x140049fec  jz      short loc_140049FFD
0x140049fee  mov     rcx, [rbx+18h]
0x140049ff2  mov     rax, rcx
0x140049ff5  and     rax, rdx
0x140049ff8  cmp     rax, rcx
0x140049ffb  jz      short loc_14004A002
0x140049ffd  mov     r9b, sil
0x14004a000  jmp     short loc_14004A005
0x14004a002  mov     r9b, 1
0x14004a005  mov     rax, [rbx+30h]
0x14004a009  mov     ecx, r8d
0x14004a00c  and     ecx, 1Fh
0x14004a00f  mov     edx, 1
0x14004a014  shl     edx, cl
0x14004a016  mov     ecx, r8d
0x14004a019  shr     rcx, 5
0x14004a01d  lea     r10, [rax+rcx*4]
0x14004a021  mov     eax, [r10]
0x14004a024  test    r9b, r9b
0x14004a027  jz      short loc_14004A02D
0x14004a029  or      edx, eax
0x14004a02b  jmp     short loc_14004A031
0x14004a02d  not     edx
0x14004a02f  and     edx, eax
0x14004a031  mov     [r10], edx
0x14004a034  inc     r8d
0x14004a037  movzx   eax, word ptr [rbx+2Ah]
0x14004a03b  cmp     r8d, eax
0x14004a03e  jb      short loc_140049FC5
0x14004a040  jmp     short loc_14004A079
0x14004a042  movzx   eax, word ptr [rbx+2Ah]
0x14004a046  mov     [rbx+24h], esi
0x14004a049  mov     [rbx+28h], sil
0x14004a04d  mov     [rbx+10h], rsi
0x14004a051  mov     [rbx+18h], rsi
0x14004a055  test    ax, ax
0x14004a058  jz      short loc_14004A079
0x14004a05a  mov     rcx, [rbx+30h]; void *
0x14004a05e  dec     eax
0x14004a060  cdq
0x14004a061  and     edx, 1Fh
0x14004a064  add     eax, edx
0x14004a066  xor     edx, edx; Val
0x14004a068  sar     eax, 5
0x14004a06b  inc     eax
0x14004a06d  movsxd  r8, eax
0x14004a070  shl     r8, 2; Size
0x14004a074  call    memset
0x14004a079  mov     rax, cs:QuicTraceRundownCallback
0x14004a080  test    rax, rax
0x14004a083  jz      short loc_14004A0A0
0x14004a085  sub     edi, 1
0x14004a088  jz      short loc_14004A08F
0x14004a08a  cmp     edi, 1
0x14004a08d  jnz     short loc_14004A0A0
0x14004a08f  lea     rcx, MICROSOFT_MSQUIC_PROVIDER_Context
0x14004a096  cmp     rbx, rcx
0x14004a099  jnz     short loc_14004A0A0
0x14004a09b  call    _guard_dispatch_icall
0x14004a0a0  mov     rbx, [rsp+28h+arg_0]
0x14004a0a5  mov     rsi, [rsp+28h+arg_8]
0x14004a0aa  add     rsp, 20h
0x14004a0ae  pop     rdi
0x14004a0af  retn
```
