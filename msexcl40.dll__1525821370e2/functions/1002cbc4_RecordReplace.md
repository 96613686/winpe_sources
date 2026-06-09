# RecordReplace

- ea: `0x1002cbc4`
- end: `0x1002cc33`
- name: `RecordReplace`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1002ce20`

## callees

- `0x100247d6`
- `0x1002c5fe`
- `0x1002cbc4`
- `0x10031f44`
- `0x10032705`

## pseudocode

```c
int __fastcall RecordReplace(_DWORD *a1, void *a2, size_t Size, _DWORD *a4)
{
  int v6; // eax
  int result; // eax
  int v8; // edi

  v6 = ChecksumRecord();
  if ( v6 == a1[9] )
  {
    result = UpdateRecord((int)a1, 0, *(_DWORD *)((char *)a1 + 30));
    if ( !result )
    {
      v8 = 0;
      if ( a2 && Size )
      {
        if ( a4 )
          *a4 = 4;
        v8 = AssignResult((char *)a1 + 30, 4u, a2, Size);
      }
      CopyBufferClear(a1);
      result = v8;
      *(_DWORD *)(a1[1] + 64) = 1;
    }
  }
  else
  {
    a1[9] = v6;
    return -1611;
  }
  return result;
}

```

## disassembly

```asm
0x1002cbc4  mov     edi, edi
0x1002cbc6  push    ebp
0x1002cbc7  mov     ebp, esp
0x1002cbc9  push    ebx
0x1002cbca  push    esi
0x1002cbcb  mov     ebx, edx
0x1002cbcd  mov     esi, ecx
0x1002cbcf  call    ChecksumRecord
0x1002cbd4  cmp     eax, [esi+24h]
0x1002cbd7  jz      short loc_1002CBE3
0x1002cbd9  mov     [esi+24h], eax
0x1002cbdc  mov     eax, 0FFFFF9B5h
0x1002cbe1  jmp     short loc_1002CC2D
0x1002cbe3  push    dword ptr [esi+1Eh]
0x1002cbe6  xor     edx, edx
0x1002cbe8  mov     ecx, esi
0x1002cbea  call    _UpdateRecord@12; UpdateRecord(x,x,x)
0x1002cbef  test    eax, eax
0x1002cbf1  jnz     short loc_1002CC2D
0x1002cbf3  push    edi
0x1002cbf4  xor     edi, edi
0x1002cbf6  test    ebx, ebx
0x1002cbf8  jz      short loc_1002CC19
0x1002cbfa  cmp     [ebp+Size], edi
0x1002cbfd  jbe     short loc_1002CC19
0x1002cbff  mov     eax, [ebp+arg_4]
0x1002cc02  push    4
0x1002cc04  pop     edx
0x1002cc05  test    eax, eax
0x1002cc07  jz      short loc_1002CC0B
0x1002cc09  mov     [eax], edx
0x1002cc0b  push    [ebp+Size]; Size
0x1002cc0e  lea     ecx, [esi+1Eh]; Src
0x1002cc11  push    ebx; void *
0x1002cc12  call    _AssignResult@16; AssignResult(x,x,x,x)
0x1002cc17  mov     edi, eax
0x1002cc19  mov     ecx, esi
0x1002cc1b  call    _CopyBufferClear@4; CopyBufferClear(x)
0x1002cc20  mov     ecx, [esi+4]
0x1002cc23  mov     eax, edi
0x1002cc25  pop     edi
0x1002cc26  mov     dword ptr [ecx+40h], 1
0x1002cc2d  pop     esi
0x1002cc2e  pop     ebx
0x1002cc2f  pop     ebp
0x1002cc30  retn    8
```
