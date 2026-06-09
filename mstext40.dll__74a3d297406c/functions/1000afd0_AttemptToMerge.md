# AttemptToMerge

- ea: `0x1000afd0`
- end: `0x1000b069`
- name: `AttemptToMerge`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1000b200`

## callees

- `0x1000af50`
- `0x1000afd0`

## pseudocode

```c
int __stdcall AttemptToMerge(int a1, int a2)
{
  int result; // eax
  int v3; // esi
  int v4; // ecx

  result = dword_10040F6C;
  v3 = 0;
  if ( dword_10040F6C )
  {
    while ( a1 != result + *(_DWORD *)(result + 4) )
    {
      if ( a1 + *(_DWORD *)(a1 + 4) == result )
      {
        v4 = *(_DWORD *)(result + 8);
        if ( v3 )
        {
          *(_DWORD *)(v3 + 8) = v4;
          *(_DWORD *)(a1 + 4) += *(_DWORD *)(result + 4);
        }
        else
        {
          *(_DWORD *)(a1 + 4) += *(_DWORD *)(result + 4);
          dword_10040F6C = v4;
        }
        return AttemptToFreePage(a1);
      }
      v3 = result;
      result = *(_DWORD *)(result + 8);
      if ( !result )
        return result;
    }
    if ( a2 )
      *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 8);
    else
      dword_10040F6C = *(_DWORD *)(a1 + 8);
    *(_DWORD *)(result + 4) += *(_DWORD *)(a1 + 4);
    return AttemptToFreePage(result);
  }
  return result;
}

```

## disassembly

```asm
0x1000afd0  mov     edx, [esp+arg_0]
0x1000afd4  mov     eax, dword_10040F6C
0x1000afd9  push    esi
0x1000afda  push    edi
0x1000afdb  mov     edi, [edx+4]
0x1000afde  xor     esi, esi
0x1000afe0  add     edi, edx
0x1000afe2  test    eax, eax
0x1000afe4  jz      short loc_1000B064
0x1000afe6  mov     ecx, [eax+4]
0x1000afe9  add     ecx, eax
0x1000afeb  cmp     edx, ecx
0x1000afed  jz      short loc_1000B033
0x1000afef  cmp     edi, eax
0x1000aff1  jz      short loc_1000B001
0x1000aff3  mov     esi, eax
0x1000aff5  mov     eax, [eax+8]
0x1000aff8  test    eax, eax
0x1000affa  jnz     short loc_1000AFE6
0x1000affc  pop     edi
0x1000affd  pop     esi
0x1000affe  retn    8
0x1000b001  mov     ecx, [eax+8]
0x1000b004  test    esi, esi
0x1000b006  jnz     short loc_1000B01F
0x1000b008  mov     eax, [eax+4]
0x1000b00b  add     [edx+4], eax
0x1000b00e  push    edx
0x1000b00f  mov     dword_10040F6C, ecx
0x1000b015  call    AttemptToFreePage
0x1000b01a  pop     edi
0x1000b01b  pop     esi
0x1000b01c  retn    8
0x1000b01f  mov     [esi+8], ecx
0x1000b022  mov     eax, [eax+4]
0x1000b025  add     [edx+4], eax
0x1000b028  push    edx
0x1000b029  call    AttemptToFreePage
0x1000b02e  pop     edi
0x1000b02f  pop     esi
0x1000b030  retn    8
0x1000b033  mov     esi, [esp+8+arg_4]
0x1000b037  mov     ecx, [edx+8]
0x1000b03a  test    esi, esi
0x1000b03c  jnz     short loc_1000B055
0x1000b03e  mov     dword_10040F6C, ecx
0x1000b044  mov     ecx, [edx+4]
0x1000b047  add     [eax+4], ecx
0x1000b04a  push    eax
0x1000b04b  call    AttemptToFreePage
0x1000b050  pop     edi
0x1000b051  pop     esi
0x1000b052  retn    8
0x1000b055  mov     [esi+8], ecx
0x1000b058  mov     ecx, [edx+4]
0x1000b05b  add     [eax+4], ecx
0x1000b05e  push    eax
0x1000b05f  call    AttemptToFreePage
0x1000b064  pop     edi
0x1000b065  pop     esi
0x1000b066  retn    8
```
