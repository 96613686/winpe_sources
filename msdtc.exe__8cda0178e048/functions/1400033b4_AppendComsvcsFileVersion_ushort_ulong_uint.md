# AppendComsvcsFileVersion(ushort *,ulong,uint *)

- ea: `0x1400033b4`
- end: `0x1400034a8`
- name: `?AppendComsvcsFileVersion@@YAXPEAGKPEAI@Z`
- size: `244`
- prototype: `void __fastcall(unsigned __int16 *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004640`

## callees

- `0x1400028f4`
- `0x1400033b4`
- `0x14000407c`
- `0x1400040dc`
- `0x1400044cc`
- `0x140006f10`

## string_xrefs

- `0x1400033d9`: `\nComsvcs.dll file version info: %s %s %s`

## pseudocode

```c
void __fastcall AppendComsvcsFileVersion(unsigned __int16 *a1, __int64 a2, unsigned int *a3)
{
  WCHAR *v4; // rax
  const wchar_t *v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rdx
  WCHAR *v8; // rcx
  unsigned int v9; // edx
  unsigned __int16 *v10; // rcx
  unsigned int v11; // r9d
  unsigned int v12; // edx
  unsigned __int16 *v13; // r8
  unsigned int v14; // [rsp+28h] [rbp-C0h]
  unsigned __int16 v15[8]; // [rsp+40h] [rbp-A8h] BYREF
  unsigned __int16 v16[8]; // [rsp+50h] [rbp-98h] BYREF
  unsigned __int16 v17[56]; // [rsp+60h] [rbp-88h] BYREF

  v4 = &Filename;
  v5 = L"\r\nComsvcs.dll file version info: %s %s %s";
  v6 = 2147483646;
  v7 = 129;
  do
  {
    if ( !v6 )
      break;
    if ( !*v5 )
      break;
    *v4++ = *v5++;
    --v6;
    --v7;
  }
  while ( v7 );
  v8 = v4 - 1;
  if ( v7 )
    v8 = v4;
  *v8 = 0;
  GetFormatString(0x3AFu, &Filename);
  GetLoadedDllFileVersion(v10, v9, v16, v11, v17, v14, v15);
  StringCchPrintfW(&word_14000F300, 0x400u, &Filename, v16, v17, v15);
  SafeAppend(&word_14000F300, v12, v13, a3);
}

```

## disassembly

```asm
0x1400033b4  push    rbx
0x1400033b6  sub     rsp, 0E0h
0x1400033bd  mov     rax, cs:__security_cookie
0x1400033c4  xor     rax, rsp
0x1400033c7  mov     [rsp+0E8h+var_18], rax
0x1400033cf  mov     rbx, r8
0x1400033d2  lea     rax, Filename
0x1400033d9  lea     r8, aComsvcsDllFile; "\r\nComsvcs.dll file version info: %s %"...
0x1400033e0  mov     ecx, 7FFFFFFEh
0x1400033e5  mov     edx, 81h
0x1400033ea  xor     r10d, r10d
0x1400033ed  test    rcx, rcx
0x1400033f0  jz      short loc_140003411
0x1400033f2  movzx   r9d, word ptr [r8]
0x1400033f6  test    r9w, r9w
0x1400033fa  jz      short loc_140003411
0x1400033fc  mov     [rax], r9w
0x140003400  add     r8, 2
0x140003404  add     rax, 2
0x140003408  dec     rcx
0x14000340b  sub     rdx, 1
0x14000340f  jnz     short loc_1400033ED
0x140003411  test    rdx, rdx
0x140003414  lea     rcx, [rax-2]
0x140003418  lea     rdx, Filename; unsigned __int16 *
0x14000341f  cmovnz  rcx, rax
0x140003423  mov     [rcx], r10w
0x140003427  mov     ecx, 3AFh; unsigned int
0x14000342c  call    ?GetFormatString@@YAXIPEAG@Z; GetFormatString(uint,ushort *)
0x140003431  lea     rax, [rsp+0E8h+var_A8]
0x140003436  mov     [rsp+0E8h+var_B8], rax; unsigned __int16 *
0x14000343b  lea     r8, [rsp+0E8h+var_98]; unsigned __int16 *
0x140003440  lea     rax, [rsp+0E8h+var_88]
0x140003445  mov     [rsp+0E8h+var_C8], rax; unsigned __int16 *
0x14000344a  call    ?GetLoadedDllFileVersion@@YAXPEAGK0K0K0@Z; GetLoadedDllFileVersion(ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *)
0x14000344f  lea     rax, [rsp+0E8h+var_A8]
0x140003454  mov     edx, 400h; unsigned __int64
0x140003459  mov     [rsp+0E8h+var_C0], rax
0x14000345e  lea     r9, [rsp+0E8h+var_98]
0x140003463  lea     rax, [rsp+0E8h+var_88]
0x140003468  lea     r8, Filename; unsigned __int16 *
0x14000346f  mov     [rsp+0E8h+var_C8], rax
0x140003474  lea     rcx, word_14000F300; unsigned __int16 *
0x14000347b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003480  mov     r9, rbx; unsigned int *
0x140003483  lea     rcx, word_14000F300; unsigned __int16 *
0x14000348a  call    ?SafeAppend@@YAXPEAGK0PEAI@Z; SafeAppend(ushort *,ulong,ushort *,uint *)
0x14000348f  mov     rcx, [rsp+0E8h+var_18]
0x140003497  xor     rcx, rsp; StackCookie
0x14000349a  call    __security_check_cookie
0x14000349f  add     rsp, 0E0h
0x1400034a6  pop     rbx
0x1400034a7  retn
```
