# MupiFindUncHardeningConfigurationEntry

- ea: `0x140015838`
- end: `0x1400158ed`
- name: `MupiFindUncHardeningConfigurationEntry`
- size: `181`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, const UNICODE_STRING *, __int64, const UNICODE_STRING **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400157a0`

## callees

- `0x140015838`
- `0x1400189b0`
- `0x14001e910`
- `0x14001e970`
- `0x14001e9d0`
- `0x14001ea40`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x1400158a9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400158a9`

## pseudocode

```c
__int64 __fastcall MupiFindUncHardeningConfigurationEntry(
        __int64 a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        __int64 a4,
        const UNICODE_STRING **a5)
{
  const UNICODE_STRING *v7; // rbx
  int v8; // edi
  __int64 i; // rax
  __int64 v10; // r8
  _OWORD v12[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v13; // [rsp+40h] [rbp-38h]

  v13 = 0;
  *a5 = 0;
  v7 = 0;
  memset(v12, 0, sizeof(v12));
  v8 = MupInitializeServerName(a2);
  if ( v8 >= 0 )
  {
    for ( i = MupiGetFirstUncHardeningConfigurationEntry(a1); ; i = MupiGetNextUncHardeningConfigurationEntry(a1, v7) )
    {
      v7 = (const UNICODE_STRING *)i;
      if ( !i )
        break;
      LOBYTE(v10) = 1;
      if ( (unsigned __int8)RfsServerNameEqualEx(i + 24, v12, v10) )
      {
        if ( RtlEqualUnicodeString(v7 + 4, a3, 1u) )
          break;
      }
    }
    v8 = 0;
  }
  RfsServerNameCleanup(v12);
  if ( v8 >= 0 )
    *a5 = v7;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140015838  push    rbx
0x14001583a  push    rbp
0x14001583b  push    rsi
0x14001583c  push    rdi
0x14001583d  push    r14
0x14001583f  sub     rsp, 50h
0x140015843  mov     r14, [rsp+78h+arg_20]
0x14001584b  mov     rsi, rcx
0x14001584e  xor     ecx, ecx
0x140015850  mov     rax, rdx
0x140015853  xorps   xmm0, xmm0
0x140015856  mov     [rsp+78h+var_38], rcx
0x14001585b  lea     rdx, [rsp+78h+var_58]
0x140015860  mov     rbp, r8
0x140015863  mov     [r14], rcx
0x140015866  xor     ebx, ebx
0x140015868  mov     rcx, rax; StringIn
0x14001586b  movups  [rsp+78h+var_58], xmm0
0x140015870  movups  [rsp+78h+var_48], xmm0
0x140015875  call    MupInitializeServerName
0x14001587a  mov     edi, eax
0x14001587c  test    eax, eax
0x14001587e  js      short loc_1400158CE
0x140015880  mov     rcx, rsi
0x140015883  call    MupiGetFirstUncHardeningConfigurationEntry
0x140015888  jmp     short loc_1400158C4
0x14001588a  lea     rcx, [rbx+18h]
0x14001588e  mov     r8b, 1
0x140015891  lea     rdx, [rsp+78h+var_58]
0x140015896  call    RfsServerNameEqualEx
0x14001589b  test    al, al
0x14001589d  jz      short loc_1400158B9
0x14001589f  lea     rcx, [rbx+40h]; String1
0x1400158a3  mov     r8b, 1; CaseInSensitive
0x1400158a6  mov     rdx, rbp; String2
0x1400158a9  call    cs:__imp_RtlEqualUnicodeString
0x1400158b0  nop     dword ptr [rax+rax+00h]
0x1400158b5  test    al, al
0x1400158b7  jnz     short loc_1400158CC
0x1400158b9  mov     rdx, rbx
0x1400158bc  mov     rcx, rsi
0x1400158bf  call    MupiGetNextUncHardeningConfigurationEntry
0x1400158c4  mov     rbx, rax
0x1400158c7  test    rax, rax
0x1400158ca  jnz     short loc_14001588A
0x1400158cc  xor     edi, edi
0x1400158ce  lea     rcx, [rsp+78h+var_58]
0x1400158d3  call    RfsServerNameCleanup
0x1400158d8  test    edi, edi
0x1400158da  js      short loc_1400158DF
0x1400158dc  mov     [r14], rbx
0x1400158df  mov     eax, edi
0x1400158e1  add     rsp, 50h
0x1400158e5  pop     r14
0x1400158e7  pop     rdi
0x1400158e8  pop     rsi
0x1400158e9  pop     rbp
0x1400158ea  pop     rbx
0x1400158eb  retn
```
