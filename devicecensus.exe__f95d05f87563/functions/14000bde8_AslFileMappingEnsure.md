# AslFileMappingEnsure

- ea: `0x14000bde8`
- end: `0x14000be99`
- name: `AslFileMappingEnsure`
- size: `177`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x14000bf5c`
- `0x14000c110`
- `0x14000c630`
- `0x14000d190`
- `0x14000d650`
- `0x14000d858`
- `0x14000d9f8`
- `0x14000e0c4`
- `0x14000e380`
- `0x14000ee0c`

## callees

- `0x140007074`
- `0x14000bde8`
- `0x14000c334`
- `0x14000c460`

## pseudocode

```c
__int64 __fastcall AslFileMappingEnsure(__int64 a1)
{
  int v3; // edi
  _DWORD *v4; // rsi
  int FileKind; // eax

  if ( *(_DWORD *)(a1 + 72) )
  {
    if ( *(_DWORD *)(a1 + 56) != 1 )
      return *(_QWORD *)(a1 + 32) == 0 ? 0xC000046D : 0;
    return 3221225758LL;
  }
  if ( *(_QWORD *)(a1 + 32) )
  {
    return 0;
  }
  else
  {
    v4 = (_DWORD *)(a1 + 56);
    if ( *(_DWORD *)(a1 + 56) == 1 )
      return 3221225758LL;
    v3 = RtlFileMapMapView(a1 + 8, 0);
    if ( v3 >= 0 )
    {
      if ( *(_BYTE *)(a1 + 51) )
      {
        *v4 = 6;
      }
      else
      {
        FileKind = AslpFileMappingGetFileKind(a1 + 8, v4);
        v3 = FileKind;
        if ( FileKind < 0 )
        {
          AslLogCallPrintf(
            1,
            "AslFileMappingEnsure",
            647,
            "AslpFileMappingGetFileKind failed %S [%x]",
            *(const wchar_t **)a1,
            FileKind);
          *v4 = 3;
        }
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000bde8  push    rbx
0x14000bdea  push    rbp
0x14000bdeb  push    rsi
0x14000bdec  push    rdi
0x14000bded  sub     rsp, 38h
0x14000bdf1  cmp     dword ptr [rcx+48h], 0
0x14000bdf5  mov     rbx, rcx
0x14000bdf8  jz      short loc_14000BE12
0x14000bdfa  cmp     dword ptr [rcx+38h], 1
0x14000bdfe  jz      short loc_14000BE26
0x14000be00  mov     rax, [rcx+20h]
0x14000be04  neg     rax
0x14000be07  sbb     eax, eax
0x14000be09  not     eax
0x14000be0b  and     eax, 0C000046Dh
0x14000be10  jmp     short loc_14000BE90
0x14000be12  cmp     qword ptr [rcx+20h], 0
0x14000be17  jz      short loc_14000BE1D
0x14000be19  xor     edi, edi
0x14000be1b  jmp     short loc_14000BE8E
0x14000be1d  lea     rsi, [rcx+38h]
0x14000be21  cmp     dword ptr [rsi], 1
0x14000be24  jnz     short loc_14000BE2D
0x14000be26  mov     eax, 0C000011Eh
0x14000be2b  jmp     short loc_14000BE90
0x14000be2d  xor     edx, edx
0x14000be2f  add     rcx, 8
0x14000be33  call    RtlFileMapMapView
0x14000be38  mov     edi, eax
0x14000be3a  test    eax, eax
0x14000be3c  js      short loc_14000BE8E
0x14000be3e  cmp     byte ptr [rbx+33h], 0
0x14000be42  jz      short loc_14000BE4C
0x14000be44  mov     dword ptr [rsi], 6
0x14000be4a  jmp     short loc_14000BE8E
0x14000be4c  mov     rdx, rsi
0x14000be4f  lea     rcx, [rbx+8]
0x14000be53  call    AslpFileMappingGetFileKind
0x14000be58  mov     edi, eax
0x14000be5a  test    eax, eax
0x14000be5c  jns     short loc_14000BE8E
0x14000be5e  mov     [rsp+58h+var_30], eax
0x14000be62  lea     r9, aAslpfilemappin; "AslpFileMappingGetFileKind failed %S [%"...
0x14000be69  mov     rax, [rbx]
0x14000be6c  lea     rdx, aAslfilemapping_3; "AslFileMappingEnsure"
0x14000be73  mov     r8d, 287h
0x14000be79  mov     [rsp+58h+var_38], rax
0x14000be7e  mov     ecx, 1
0x14000be83  call    AslLogCallPrintf
0x14000be88  mov     dword ptr [rsi], 3
0x14000be8e  mov     eax, edi
0x14000be90  add     rsp, 38h
0x14000be94  pop     rdi
0x14000be95  pop     rsi
0x14000be96  pop     rbp
0x14000be97  pop     rbx
0x14000be98  retn
```
