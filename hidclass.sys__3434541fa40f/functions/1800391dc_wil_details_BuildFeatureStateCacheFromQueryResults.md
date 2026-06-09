# wil_details_BuildFeatureStateCacheFromQueryResults

- ea: `0x1800391dc`
- end: `0x180039233`
- name: `wil_details_BuildFeatureStateCacheFromQueryResults`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180039510`
- `0x180045138`

## callees

- `0x1800391dc`

## pseudocode

```c
__int64 __fastcall wil_details_BuildFeatureStateCacheFromQueryResults(int a1, __int64 a2, _QWORD *a3)
{
  __int64 result; // rax
  int v4; // edx
  int v5; // edx

  if ( a1 == -2147483614 || a1 == -1073741275 )
  {
    result = 0;
    *a3 = 0;
    goto LABEL_9;
  }
  result = 0;
  *a3 = 0;
  if ( !a1 )
  {
    result = *(_DWORD *)(a2 + 4) & 0xB0;
    v4 = result | (4 * (*(_DWORD *)(a2 + 4) & 0x40));
    goto LABEL_7;
  }
  if ( a1 != 279 )
  {
LABEL_9:
    v5 = 518;
    goto LABEL_10;
  }
  v4 = *(_DWORD *)(a2 + 4) & 0x80;
LABEL_7:
  v5 = (8 * v4) | 0x206;
LABEL_10:
  *(_DWORD *)a3 = v5;
  return result;
}

```

## disassembly

```asm
0x1800391dc  cmp     ecx, 80000022h
0x1800391e2  jz      short loc_180039225
0x1800391e4  cmp     ecx, 0C0000225h
0x1800391ea  jz      short loc_180039225
0x1800391ec  xor     eax, eax
0x1800391ee  mov     [r8], rax
0x1800391f1  test    ecx, ecx
0x1800391f3  jz      short loc_180039208
0x1800391f5  cmp     ecx, 117h
0x1800391fb  jnz     short loc_18003922A
0x1800391fd  mov     edx, [rdx+4]
0x180039200  and     edx, 80h
0x180039206  jmp     short loc_18003921A
0x180039208  mov     eax, [rdx+4]
0x18003920b  mov     edx, eax
0x18003920d  and     edx, 40h
0x180039210  and     eax, 0B0h
0x180039215  shl     edx, 2
0x180039218  or      edx, eax
0x18003921a  shl     edx, 3
0x18003921d  or      edx, 206h
0x180039223  jmp     short loc_18003922F
0x180039225  xor     eax, eax
0x180039227  mov     [r8], rax
0x18003922a  mov     edx, 206h
0x18003922f  mov     [r8], edx
0x180039232  retn
```
