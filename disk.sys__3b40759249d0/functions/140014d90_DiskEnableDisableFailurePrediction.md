# DiskEnableDisableFailurePrediction

- ea: `0x140014d90`
- end: `0x140014de1`
- name: `DiskEnableDisableFailurePrediction`
- size: `81`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e5f8`
- `0x14001016c`
- `0x140010490`

## callees

- `0x1400028b0`
- `0x140003410`
- `0x140014d90`

## pseudocode

```c
__int64 __fastcall DiskEnableDisableFailurePrediction(__int64 a1, char a2)
{
  __int64 v2; // rdi
  int v4; // edx
  int v5; // edx
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 96);
  v4 = *(_DWORD *)(v2 + 16);
  if ( v4 == 2 )
  {
    if ( a2 )
      result = DiskEnableSmart(a1);
    else
      result = DiskDisableSmart();
    if ( (int)result >= 0 )
      *(_BYTE *)(v2 + 22) = a2;
  }
  else
  {
    v5 = v4 - 1;
    if ( !v5 || v5 == 2 )
      return 0;
    else
      return 3221225488LL;
  }
  return result;
}

```

## disassembly

```asm
0x140014d90  mov     [rsp+arg_0], rbx
0x140014d95  push    rdi
0x140014d96  sub     rsp, 20h
0x140014d9a  mov     rdi, [rcx+60h]
0x140014d9e  movzx   ebx, dl
0x140014da1  mov     edx, [rdi+10h]
0x140014da4  cmp     edx, 2
0x140014da7  jz      short loc_140014DBE
0x140014da9  sub     edx, 1
0x140014dac  jz      short loc_140014DBA
0x140014dae  cmp     edx, 2
0x140014db1  jz      short loc_140014DBA
0x140014db3  mov     eax, 0C0000010h
0x140014db8  jmp     short loc_140014DD5
0x140014dba  xor     eax, eax
0x140014dbc  jmp     short loc_140014DD5
0x140014dbe  test    bl, bl
0x140014dc0  jz      short loc_140014DC9
0x140014dc2  call    DiskEnableSmart
0x140014dc7  jmp     short loc_140014DCE
0x140014dc9  call    DiskDisableSmart
0x140014dce  test    eax, eax
0x140014dd0  js      short loc_140014DD5
0x140014dd2  mov     [rdi+16h], bl
0x140014dd5  mov     rbx, [rsp+28h+arg_0]
0x140014dda  add     rsp, 20h
0x140014dde  pop     rdi
0x140014ddf  retn
```
