# ProcessRdmaReadCompletion

- ea: `0x18004fb58`
- end: `0x18004fd15`
- name: `ProcessRdmaReadCompletion`
- size: `445`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003b760`
- `0x1800485dc`

## callees

- `0x180038104`
- `0x180038c40`
- `0x18003ae8c`
- `0x180042128`
- `0x180045f50`
- `0x180049ba8`
- `0x18004fb58`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fb82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fbec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fc78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fb82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fbec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fc78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fba2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fba2`

## pseudocode

```c
void __fastcall ProcessRdmaReadCompletion(__int64 a1, unsigned int a2, int a3)
{
  __int64 v3; // rdi
  char v4; // r15
  __int64 v8; // rcx
  char v9; // al
  __int64 v10; // rdx
  int v11; // ecx
  unsigned int v12; // r8d
  __int64 v13; // rbx
  unsigned int v14; // [rsp+70h] [rbp+8h] BYREF

  v3 = 0;
  v4 = 0;
  v14 = 0;
  if ( !*(_DWORD *)(a1 + 468) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
    CheckRsMode(a1, 2 - (unsigned int)(a3 != 0));
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  }
  v8 = *(_QWORD *)(a1 + 400);
  if ( v8 != a1 + 400 )
  {
    v9 = *(_BYTE *)(a1 + 800);
    if ( (v9 & 4) == 0 && !*(_DWORD *)(a1 + 136) )
    {
      v3 = v8 - 16;
      if ( (v9 & 0x40) == 0 || *(_BYTE *)(v3 + 129) )
      {
        v11 = *(_DWORD *)(v3 + 92);
        if ( (*(_BYTE *)(v3 + 92) & 0x84) != 0x84 )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
          if ( (xmmword_180063D60 & 2) == 0 )
            return;
          v10 = 34;
          goto LABEL_21;
        }
        v12 = *(_DWORD *)(*(_QWORD *)(v3 + 120) + 80LL);
        if ( a2 <= v12 )
        {
          *(_DWORD *)(v3 + 40) += a2;
          *(_DWORD *)(v3 + 84) += a2;
        }
        else
        {
          if ( (xmmword_180063D60 & 2) != 0 )
          {
            WPP_SF_ddq(1025, 35, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids, a2, v12, v3);
            v11 = *(_DWORD *)(v3 + 92);
          }
          v4 = 1;
        }
        *(_DWORD *)(v3 + 92) = v11 & 0xFFFFFF7B;
      }
      else
      {
        v3 = 0;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  if ( !v3 )
  {
    if ( (xmmword_180063D60 & 2) == 0 )
      return;
    v10 = 36;
LABEL_21:
    WPP_SF_(1025, v10, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids);
    return;
  }
  v13 = *(_QWORD *)(v3 + 120);
  if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)(a1 + 16) + 328LL))(
         *(_QWORD *)(a1 + 104),
         *(_QWORD *)(v13 + 96),
         *(unsigned int *)(*(_QWORD *)(a1 + 16) + 20LL),
         &v14) == -1
    && (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_d(1025, 37, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids, v14);
  }
  PostProcessRdmaSend(v13, 0, 0);
  if ( v4 )
    AbortSanConnection(a1);
}

```

## disassembly

```asm
0x18004fb58  push    rbx
0x18004fb5a  push    rbp
0x18004fb5b  push    rsi
0x18004fb5c  push    rdi
0x18004fb5d  push    r14
0x18004fb5f  push    r15
0x18004fb61  sub     rsp, 38h
0x18004fb65  xor     edi, edi
0x18004fb67  xor     r15b, r15b
0x18004fb6a  mov     r14d, r8d
0x18004fb6d  mov     ebp, edx
0x18004fb6f  mov     rsi, rcx
0x18004fb72  mov     [rsp+68h+arg_0], edi
0x18004fb76  cmp     [rcx+1D4h], edi
0x18004fb7c  jnz     short loc_18004FBAE
0x18004fb7e  add     rcx, 30h ; '0'; lpCriticalSection
0x18004fb82  call    cs:__imp_LeaveCriticalSection
0x18004fb89  nop     dword ptr [rax+rax+00h]
0x18004fb8e  neg     r14d
0x18004fb91  mov     rcx, rsi
0x18004fb94  sbb     edx, edx
0x18004fb96  add     edx, 2
0x18004fb99  call    CheckRsMode
0x18004fb9e  lea     rcx, [rsi+30h]; lpCriticalSection
0x18004fba2  call    cs:__imp_EnterCriticalSection
0x18004fba9  nop     dword ptr [rax+rax+00h]
0x18004fbae  lea     rax, [rsi+190h]
0x18004fbb5  mov     r14d, 401h
0x18004fbbb  mov     rcx, [rax]
0x18004fbbe  cmp     rcx, rax
0x18004fbc1  jz      short loc_18004FBE8
0x18004fbc3  mov     al, [rsi+320h]
0x18004fbc9  test    al, 4
0x18004fbcb  jnz     short loc_18004FBE8
0x18004fbcd  cmp     [rsi+88h], edi
0x18004fbd3  jnz     short loc_18004FBE8
0x18004fbd5  lea     rdi, [rcx-10h]
0x18004fbd9  test    al, 40h
0x18004fbdb  jz      short loc_18004FC13
0x18004fbdd  cmp     [rdi+81h], r15b
0x18004fbe4  jnz     short loc_18004FC13
0x18004fbe6  xor     edi, edi
0x18004fbe8  lea     rcx, [rsi+30h]; lpCriticalSection
0x18004fbec  call    cs:__imp_LeaveCriticalSection
0x18004fbf3  nop     dword ptr [rax+rax+00h]
0x18004fbf8  test    rdi, rdi
0x18004fbfb  jnz     loc_18004FCA3
0x18004fc01  test    byte ptr cs:xmmword_180063D60, 2
0x18004fc08  jz      loc_18004FD07
0x18004fc0e  lea     edx, [rdi+24h]
0x18004fc11  jmp     short loc_18004FC92
0x18004fc13  mov     ecx, [rdi+5Ch]
0x18004fc16  mov     eax, ecx
0x18004fc18  and     eax, 84h
0x18004fc1d  cmp     al, 84h
0x18004fc1f  jnz     short loc_18004FC74
0x18004fc21  mov     rax, [rdi+78h]
0x18004fc25  mov     r8d, [rax+50h]
0x18004fc29  cmp     ebp, r8d
0x18004fc2c  jbe     short loc_18004FC60
0x18004fc2e  test    byte ptr cs:xmmword_180063D60, 2
0x18004fc35  jz      short loc_18004FC5B
0x18004fc37  mov     [rsp+68h+var_40], rdi
0x18004fc3c  mov     edx, 23h ; '#'
0x18004fc41  mov     [rsp+68h+var_48], r8d
0x18004fc46  mov     ecx, r14d
0x18004fc49  lea     r8, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids
0x18004fc50  mov     r9d, ebp
0x18004fc53  call    WPP_SF_ddq
0x18004fc58  mov     ecx, [rdi+5Ch]
0x18004fc5b  mov     r15b, 1
0x18004fc5e  jmp     short loc_18004FC66
0x18004fc60  add     [rdi+28h], ebp
0x18004fc63  add     [rdi+54h], ebp
0x18004fc66  and     ecx, 0FFFFFF7Bh
0x18004fc6c  mov     [rdi+5Ch], ecx
0x18004fc6f  jmp     loc_18004FBE8
0x18004fc74  lea     rcx, [rsi+30h]; lpCriticalSection
0x18004fc78  call    cs:__imp_LeaveCriticalSection
0x18004fc7f  nop     dword ptr [rax+rax+00h]
0x18004fc84  test    byte ptr cs:xmmword_180063D60, 2
0x18004fc8b  jz      short loc_18004FD07
0x18004fc8d  mov     edx, 22h ; '"'
0x18004fc92  mov     ecx, r14d
0x18004fc95  lea     r8, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids
0x18004fc9c  call    WPP_SF_
0x18004fca1  jmp     short loc_18004FD07
0x18004fca3  mov     r8, [rsi+10h]
0x18004fca7  lea     r9, [rsp+68h+arg_0]
0x18004fcac  mov     rbx, [rdi+78h]
0x18004fcb0  mov     rcx, [rsi+68h]
0x18004fcb4  mov     rax, [r8+148h]
0x18004fcbb  mov     r8d, [r8+14h]
0x18004fcbf  mov     rdx, [rbx+60h]
0x18004fcc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fcc8  cmp     eax, 0FFFFFFFFh
0x18004fccb  jnz     short loc_18004FCED
0x18004fccd  test    byte ptr cs:xmmword_180063D60, 2
0x18004fcd4  jz      short loc_18004FCED
0x18004fcd6  mov     r9d, [rsp+68h+arg_0]
0x18004fcdb  lea     edx, [rax+26h]
0x18004fcde  mov     ecx, r14d
0x18004fce1  lea     r8, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids
0x18004fce8  call    WPP_SF_d
0x18004fced  xor     r8d, r8d
0x18004fcf0  xor     edx, edx
0x18004fcf2  mov     rcx, rbx
0x18004fcf5  call    PostProcessRdmaSend
0x18004fcfa  test    r15b, r15b
0x18004fcfd  jz      short loc_18004FD07
0x18004fcff  mov     rcx, rsi
0x18004fd02  call    AbortSanConnection
0x18004fd07  add     rsp, 38h
0x18004fd0b  pop     r15
0x18004fd0d  pop     r14
0x18004fd0f  pop     rdi
0x18004fd10  pop     rsi
0x18004fd11  pop     rbp
0x18004fd12  pop     rbx
0x18004fd13  retn
```
