# MupiFindUncHardeningConfigurationEntry

- ea: `0x1400157e8`
- end: `0x14001589d`
- name: `MupiFindUncHardeningConfigurationEntry`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140015750`

## callees

- `0x1400157e8`
- `0x140018960`
- `0x14001e8c0`
- `0x14001e920`
- `0x14001e980`
- `0x14001e9f0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140015859`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015859`

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
0x1400157e8  push    rbx
0x1400157ea  push    rbp
0x1400157eb  push    rsi
0x1400157ec  push    rdi
0x1400157ed  push    r14
0x1400157ef  sub     rsp, 50h
0x1400157f3  mov     r14, [rsp+78h+arg_20]
0x1400157fb  mov     rsi, rcx
0x1400157fe  xor     ecx, ecx
0x140015800  mov     rax, rdx
0x140015803  xorps   xmm0, xmm0
0x140015806  mov     [rsp+78h+var_38], rcx
0x14001580b  lea     rdx, [rsp+78h+var_58]
0x140015810  mov     rbp, r8
0x140015813  mov     [r14], rcx
0x140015816  xor     ebx, ebx
0x140015818  mov     rcx, rax; StringIn
0x14001581b  movups  [rsp+78h+var_58], xmm0
0x140015820  movups  [rsp+78h+var_48], xmm0
0x140015825  call    MupInitializeServerName
0x14001582a  mov     edi, eax
0x14001582c  test    eax, eax
0x14001582e  js      short loc_14001587E
0x140015830  mov     rcx, rsi
0x140015833  call    MupiGetFirstUncHardeningConfigurationEntry
0x140015838  jmp     short loc_140015874
0x14001583a  lea     rcx, [rbx+18h]
0x14001583e  mov     r8b, 1
0x140015841  lea     rdx, [rsp+78h+var_58]
0x140015846  call    RfsServerNameEqualEx
0x14001584b  test    al, al
0x14001584d  jz      short loc_140015869
0x14001584f  lea     rcx, [rbx+40h]; String1
0x140015853  mov     r8b, 1; CaseInSensitive
0x140015856  mov     rdx, rbp; String2
0x140015859  call    cs:__imp_RtlEqualUnicodeString
0x140015860  nop     dword ptr [rax+rax+00h]
0x140015865  test    al, al
0x140015867  jnz     short loc_14001587C
0x140015869  mov     rdx, rbx
0x14001586c  mov     rcx, rsi
0x14001586f  call    MupiGetNextUncHardeningConfigurationEntry
0x140015874  mov     rbx, rax
0x140015877  test    rax, rax
0x14001587a  jnz     short loc_14001583A
0x14001587c  xor     edi, edi
0x14001587e  lea     rcx, [rsp+78h+var_58]
0x140015883  call    RfsServerNameCleanup
0x140015888  test    edi, edi
0x14001588a  js      short loc_14001588F
0x14001588c  mov     [r14], rbx
0x14001588f  mov     eax, edi
0x140015891  add     rsp, 50h
0x140015895  pop     r14
0x140015897  pop     rdi
0x140015898  pop     rsi
0x140015899  pop     rbp
0x14001589a  pop     rbx
0x14001589b  retn
```
