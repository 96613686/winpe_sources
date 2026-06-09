# AslFileMappingEnsure

- ea: `0x18000dcf4`
- end: `0x18000dda5`
- name: `AslFileMappingEnsure`
- size: `177`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d258`
- `0x18000de68`
- `0x18000e01c`
- `0x18000fd14`
- `0x1800101d4`
- `0x1800103dc`
- `0x18001057c`
- `0x180010c48`
- `0x180010f04`
- `0x180011990`

## callees

- `0x18000dcf4`
- `0x18000e240`
- `0x180012918`
- `0x180013814`

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
0x18000dcf4  push    rbx
0x18000dcf6  push    rbp
0x18000dcf7  push    rsi
0x18000dcf8  push    rdi
0x18000dcf9  sub     rsp, 38h
0x18000dcfd  cmp     dword ptr [rcx+48h], 0
0x18000dd01  mov     rbx, rcx
0x18000dd04  jz      short loc_18000DD1E
0x18000dd06  cmp     dword ptr [rcx+38h], 1
0x18000dd0a  jz      short loc_18000DD32
0x18000dd0c  mov     rax, [rcx+20h]
0x18000dd10  neg     rax
0x18000dd13  sbb     eax, eax
0x18000dd15  not     eax
0x18000dd17  and     eax, 0C000046Dh
0x18000dd1c  jmp     short loc_18000DD9C
0x18000dd1e  cmp     qword ptr [rcx+20h], 0
0x18000dd23  jz      short loc_18000DD29
0x18000dd25  xor     edi, edi
0x18000dd27  jmp     short loc_18000DD9A
0x18000dd29  lea     rsi, [rcx+38h]
0x18000dd2d  cmp     dword ptr [rsi], 1
0x18000dd30  jnz     short loc_18000DD39
0x18000dd32  mov     eax, 0C000011Eh
0x18000dd37  jmp     short loc_18000DD9C
0x18000dd39  xor     edx, edx
0x18000dd3b  add     rcx, 8
0x18000dd3f  call    RtlFileMapMapView
0x18000dd44  mov     edi, eax
0x18000dd46  test    eax, eax
0x18000dd48  js      short loc_18000DD9A
0x18000dd4a  cmp     byte ptr [rbx+33h], 0
0x18000dd4e  jz      short loc_18000DD58
0x18000dd50  mov     dword ptr [rsi], 6
0x18000dd56  jmp     short loc_18000DD9A
0x18000dd58  mov     rdx, rsi
0x18000dd5b  lea     rcx, [rbx+8]
0x18000dd5f  call    AslpFileMappingGetFileKind
0x18000dd64  mov     edi, eax
0x18000dd66  test    eax, eax
0x18000dd68  jns     short loc_18000DD9A
0x18000dd6a  mov     [rsp+58h+var_30], eax
0x18000dd6e  lea     r9, aAslpfilemappin; "AslpFileMappingGetFileKind failed %S [%"...
0x18000dd75  mov     rax, [rbx]
0x18000dd78  lea     rdx, aAslfilemapping_4; "AslFileMappingEnsure"
0x18000dd7f  mov     r8d, 287h
0x18000dd85  mov     [rsp+58h+var_38], rax
0x18000dd8a  mov     ecx, 1
0x18000dd8f  call    AslLogCallPrintf
0x18000dd94  mov     dword ptr [rsi], 3
0x18000dd9a  mov     eax, edi
0x18000dd9c  add     rsp, 38h
0x18000dda0  pop     rdi
0x18000dda1  pop     rsi
0x18000dda2  pop     rbp
0x18000dda3  pop     rbx
0x18000dda4  retn
```
