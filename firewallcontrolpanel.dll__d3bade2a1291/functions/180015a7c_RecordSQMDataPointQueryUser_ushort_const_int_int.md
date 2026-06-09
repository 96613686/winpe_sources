# RecordSQMDataPointQueryUser(ushort const *,int,int)

- ea: `0x180015a7c`
- end: `0x180015b0c`
- name: `?RecordSQMDataPointQueryUser@@YAXPEBGHH@Z`
- size: `144`
- prototype: `void __fastcall(const unsigned __int16 *, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180011ed4`
- `0x180012270`

## callees

- `0x180015a7c`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x180015af6`
- `ntdll!WinSqmAddToStream` at `0x180015af6`
- `SHLWAPI!PathFindFileNameW` at `0x180015aa5`
- `SHLWAPI!PathFindFileNameW` at `0x180015aa5`

## pseudocode

```c
void __fastcall RecordSQMDataPointQueryUser(const unsigned __int16 *a1, int a2, int a3)
{
  LPWSTR FileNameW; // rax
  int v6; // [rsp+20h] [rbp-28h] BYREF
  __int128 v7; // [rsp+28h] [rbp-20h]
  __int64 v8; // [rsp+38h] [rbp-10h]

  v8 = 0;
  v6 = 0;
  v7 = 0;
  FileNameW = PathFindFileNameW(a1);
  if ( !FileNameW || !*FileNameW )
    FileNameW = L"(null)";
  *(_QWORD *)&v7 = FileNameW;
  DWORD2(v7) = 1;
  v6 = 2;
  LODWORD(v8) = a2 != 0;
  WinSqmAddToStream(0, a3 != 0 ? 6404 : 3096, 2, &v6);
}

```

## disassembly

```asm
0x180015a7c  mov     [rsp+arg_0], rbx
0x180015a81  mov     [rsp+arg_8], rsi
0x180015a86  push    rdi
0x180015a87  sub     rsp, 40h
0x180015a8b  xorps   xmm0, xmm0
0x180015a8e  xor     eax, eax
0x180015a90  xor     esi, esi
0x180015a92  mov     [rsp+48h+var_10], rax
0x180015a97  mov     [rsp+48h+var_28], esi
0x180015a9b  mov     ebx, r8d
0x180015a9e  movups  [rsp+48h+var_20], xmm0
0x180015aa3  mov     edi, edx
0x180015aa5  call    cs:__imp_PathFindFileNameW
0x180015aab  test    rax, rax
0x180015aae  jz      short loc_180015AB5
0x180015ab0  cmp     [rax], si
0x180015ab3  jnz     short loc_180015ABC
0x180015ab5  lea     rax, aNull; "(null)"
0x180015abc  mov     qword ptr [rsp+48h+var_20], rax
0x180015ac1  lea     r9, [rsp+48h+var_28]
0x180015ac6  test    edi, edi
0x180015ac8  mov     dword ptr [rsp+48h+var_20+8], 1
0x180015ad0  mov     eax, esi
0x180015ad2  mov     r8d, 2
0x180015ad8  setnz   al
0x180015adb  mov     [rsp+48h+var_28], r8d
0x180015ae0  neg     ebx
0x180015ae2  mov     dword ptr [rsp+48h+var_10], eax
0x180015ae6  sbb     edx, edx
0x180015ae8  xor     ecx, ecx
0x180015aea  and     edx, 0CECh
0x180015af0  add     edx, 0C18h
0x180015af6  call    cs:__imp_WinSqmAddToStream
0x180015afc  mov     rbx, [rsp+48h+arg_0]
0x180015b01  mov     rsi, [rsp+48h+arg_8]
0x180015b06  add     rsp, 40h
0x180015b0a  pop     rdi
0x180015b0b  retn
```
