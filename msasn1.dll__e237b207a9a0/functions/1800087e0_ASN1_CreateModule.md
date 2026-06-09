# ASN1_CreateModule

- ea: `0x1800087e0`
- end: `0x18000889a`
- name: `ASN1_CreateModule`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800087e0`
- `0x1800088a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008859`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008859`

## pseudocode

```c
_DWORD *__fastcall ASN1_CreateModule(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9)
{
  _DWORD *v9; // rbx
  _DWORD *v14; // rax

  v9 = 0;
  if ( !g_bIsConfigInitialized )
    ASN1p_ReadConfig();
  if ( a5 )
  {
    if ( a6 )
    {
      if ( a7 )
      {
        if ( a8 )
        {
          v14 = LocalAlloc(0x40u, 0x30u);
          v9 = v14;
          if ( v14 )
          {
            *v14 = a9;
            v14[1] = a2;
            v14[2] = a3;
            v14[3] = a4;
            *((_QWORD *)v14 + 2) = a7;
            *((_QWORD *)v14 + 3) = a8;
            if ( (a2 & 0x700) != 0 )
            {
              *((_QWORD *)v14 + 4) = a5;
              *((_QWORD *)v14 + 5) = a6;
            }
          }
        }
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800087e0  push    rbx
0x1800087e2  push    rbp
0x1800087e3  push    rsi
0x1800087e4  push    rdi
0x1800087e5  push    r12
0x1800087e7  push    r13
0x1800087e9  push    r14
0x1800087eb  push    r15
0x1800087ed  sub     rsp, 28h
0x1800087f1  xor     ebx, ebx
0x1800087f3  mov     r12d, r9d
0x1800087f6  cmp     cs:g_bIsConfigInitialized, ebx
0x1800087fc  mov     r13d, r8d
0x1800087ff  mov     r15d, edx
0x180008802  jnz     short loc_180008809
0x180008804  call    ASN1p_ReadConfig
0x180008809  mov     rdi, [rsp+68h+arg_20]
0x180008811  test    rdi, rdi
0x180008814  jnz     short loc_18000882A
0x180008816  mov     rax, rbx
0x180008819  add     rsp, 28h
0x18000881d  pop     r15
0x18000881f  pop     r14
0x180008821  pop     r13
0x180008823  pop     r12
0x180008825  pop     rdi
0x180008826  pop     rsi
0x180008827  pop     rbp
0x180008828  pop     rbx
0x180008829  retn
0x18000882a  mov     rsi, [rsp+68h+arg_28]
0x180008832  test    rsi, rsi
0x180008835  jz      short loc_180008816
0x180008837  mov     rbp, [rsp+68h+arg_30]
0x18000883f  test    rbp, rbp
0x180008842  jz      short loc_180008816
0x180008844  mov     r14, [rsp+68h+arg_38]
0x18000884c  test    r14, r14
0x18000884f  jz      short loc_180008816
0x180008851  mov     edx, 30h ; '0'; uBytes
0x180008856  lea     ecx, [rdx+10h]; uFlags
0x180008859  call    cs:__imp_LocalAlloc
0x18000885f  mov     rbx, rax
0x180008862  test    rax, rax
0x180008865  jz      short loc_180008816
0x180008867  mov     ecx, [rsp+68h+arg_40]
0x18000886e  mov     [rax], ecx
0x180008870  mov     [rax+4], r15d
0x180008874  mov     [rax+8], r13d
0x180008878  mov     [rax+0Ch], r12d
0x18000887c  mov     [rax+10h], rbp
0x180008880  mov     [rax+18h], r14
0x180008884  test    r15d, 700h
0x18000888b  jz      short loc_180008816
0x18000888d  mov     [rax+20h], rdi
0x180008891  mov     [rax+28h], rsi
0x180008895  jmp     loc_180008816
```
