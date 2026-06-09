# LipsStateIpsecPolicyDelete

- ea: `0x180047094`
- end: `0x18004710a`
- name: `LipsStateIpsecPolicyDelete`
- size: `118`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180044ea4`
- `0x180044f5c`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x180047094`
- `0x180047110`
- `0x1800482dc`

## string_xrefs

- `0x1800470f1`: `LipsStateIpsecPolicyDelete`

## pseudocode

```c
__int64 __fastcall LipsStateIpsecPolicyDelete(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v2; // ebx

  v1 = a1 + 56;
  v2 = LipsBfeProviderContextDelete(*(GUID **)(a1 + 56));
  if ( v2 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_354a146e6ff73aa2a7adbc2af83c8eac_Traceguids, v2);
  LipsStateIpsecPolicyDestroy(v1);
  if ( v2 )
    return LipsReportError(v2, (int)"LipsStateIpsecPolicyDelete");
  else
    return 0;
}

```

## disassembly

```asm
0x180047094  mov     [rsp+arg_0], rbx
0x180047099  push    rdi
0x18004709a  sub     rsp, 20h
0x18004709e  lea     rdi, [rcx+38h]
0x1800470a2  mov     rcx, [rdi]; key
0x1800470a5  call    LipsBfeProviderContextDelete
0x1800470aa  mov     ebx, eax
0x1800470ac  test    eax, eax
0x1800470ae  jz      short loc_1800470E1
0x1800470b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800470b7  lea     rax, WPP_GLOBAL_Control
0x1800470be  cmp     rcx, rax
0x1800470c1  jz      short loc_1800470E1
0x1800470c3  test    byte ptr [rcx+1Ch], 10h
0x1800470c7  jz      short loc_1800470E1
0x1800470c9  mov     rcx, [rcx+10h]
0x1800470cd  lea     r8, WPP_354a146e6ff73aa2a7adbc2af83c8eac_Traceguids
0x1800470d4  mov     edx, 0Dh
0x1800470d9  mov     r9d, ebx
0x1800470dc  call    WPP_SF_d
0x1800470e1  mov     rcx, rdi
0x1800470e4  call    LipsStateIpsecPolicyDestroy
0x1800470e9  test    ebx, ebx
0x1800470eb  jnz     short loc_1800470F1
0x1800470ed  xor     eax, eax
0x1800470ef  jmp     short loc_1800470FF
0x1800470f1  lea     rdx, aLipsstateipsec_1; "LipsStateIpsecPolicyDelete"
0x1800470f8  mov     ecx, ebx
0x1800470fa  call    LipsReportError
0x1800470ff  mov     rbx, [rsp+28h+arg_0]
0x180047104  add     rsp, 20h
0x180047108  pop     rdi
0x180047109  retn
```
