# SmbTransactBuildHeader

- ea: `0x1400512e0`
- end: `0x1400513c2`
- name: `SmbTransactBuildHeader`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14003ffe0`

## callees

- `0x1400478f0`
- `0x1400512e0`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcessId` at `0x14005136d`
- `ntoskrnl!IoGetRequestorProcessId` at `0x14005136d`

## pseudocode

```c
__int64 __fastcall SmbTransactBuildHeader(__int64 a1, char a2, _WORD *a3)
{
  __int64 result; // rax
  IRP *v7; // rcx
  ULONG RequestorProcessId; // eax
  int v9; // [rsp+30h] [rbp-38h] BYREF
  _BYTE *v10; // [rsp+38h] [rbp-30h] BYREF
  __int64 v11; // [rsp+88h] [rbp+20h] BYREF

  v9 = 0;
  v10 = 0;
  result = SmbCeBuildSmbHeader(a1, (_DWORD)a3, 32, (unsigned int)&v9, (__int64)&v11, (__int64)&v10);
  if ( !(_DWORD)result )
  {
    *v10 = a2;
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 80) + 420LL) & 0x40000) != 0 && (*(_WORD *)(a1 + 510) & 0x800) == 0 )
    {
      v7 = *(IRP **)(*(_QWORD *)(a1 + 24) + 40LL);
      if ( v7 )
        RequestorProcessId = IoGetRequestorProcessId(v7);
      else
        RequestorProcessId = 65279;
      *(_DWORD *)(a1 + 72) |= 0x4000u;
      a3[13] = RequestorProcessId;
      a3[6] = HIWORD(RequestorProcessId);
    }
    if ( _bittest16((const signed __int16 *)(a1 + 510), 0xBu) )
      a3[5] &= ~0x4000u;
    if ( _bittest16((const signed __int16 *)(a1 + 510), 9u) )
      a3[5] |= 0x1000u;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400512e0  mov     r11, rsp
0x1400512e3  push    rbx
0x1400512e4  push    rbp
0x1400512e5  push    rsi
0x1400512e6  push    rdi
0x1400512e7  sub     rsp, 48h
0x1400512eb  xor     eax, eax
0x1400512ed  lea     r9, [r11-38h]
0x1400512f1  mov     [rsp+68h+var_38], eax
0x1400512f5  mov     rsi, r8
0x1400512f8  mov     [r11-30h], rax
0x1400512fc  movzx   ebp, dl
0x1400512ff  lea     rax, [r11-30h]
0x140051303  mov     r8d, 20h ; ' '
0x140051309  mov     [r11-40h], rax
0x14005130d  mov     rdx, rsi
0x140051310  lea     rax, [r11+20h]
0x140051314  mov     rbx, rcx
0x140051317  mov     [r11-48h], rax
0x14005131b  call    SmbCeBuildSmbHeader
0x140051320  mov     edi, eax
0x140051322  test    eax, eax
0x140051324  jz      short loc_140051330
0x140051326  add     rsp, 48h
0x14005132a  pop     rdi
0x14005132b  pop     rsi
0x14005132c  pop     rbp
0x14005132d  pop     rbx
0x14005132e  retn
0x140051330  mov     rcx, [rsp+68h+var_30]
0x140051335  mov     eax, 0Bh
0x14005133a  mov     [rcx], bpl
0x14005133d  mov     rcx, [rbx+50h]
0x140051341  test    dword ptr [rcx+1A4h], 40000h
0x14005134b  movzx   ecx, word ptr [rbx+1FEh]
0x140051352  setnz   dl
0x140051355  bt      cx, ax
0x140051359  setnb   cl
0x14005135c  test    cl, dl
0x14005135e  jz      short loc_14005138B
0x140051360  mov     rax, [rbx+18h]
0x140051364  mov     rcx, [rax+28h]; Irp
0x140051368  test    rcx, rcx
0x14005136b  jz      short loc_1400513A5
0x14005136d  call    cs:__imp_IoGetRequestorProcessId
0x140051374  nop     dword ptr [rax+rax+00h]
0x140051379  or      dword ptr [rbx+48h], 4000h
0x140051380  mov     [rsi+1Ah], ax
0x140051384  shr     eax, 10h
0x140051387  mov     [rsi+0Ch], ax
0x14005138b  bt      word ptr [rbx+1FEh], 0Bh
0x140051394  jb      short loc_1400513AC
0x140051396  bt      word ptr [rbx+1FEh], 9
0x14005139f  jb      short loc_1400513B7
0x1400513a1  mov     eax, edi
0x1400513a3  jmp     short loc_140051326
0x1400513a5  mov     eax, 0FEFFh
0x1400513aa  jmp     short loc_140051379
0x1400513ac  mov     eax, 0BFFFh
0x1400513b1  and     [rsi+0Ah], ax
0x1400513b5  jmp     short loc_140051396
0x1400513b7  mov     eax, 1000h
0x1400513bc  or      [rsi+0Ah], ax
0x1400513c0  jmp     short loc_1400513A1
```
