# AppendComsvcsFileVersion(ushort *,ulong,uint *)

- ea: `0x18000ea1c`
- end: `0x18000eb10`
- name: `?AppendComsvcsFileVersion@@YAXPEAGKPEAI@Z`
- size: `244`
- prototype: `void __fastcall(unsigned __int16 *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fca8`

## callees

- `0x18000e000`
- `0x18000ea1c`
- `0x18000f6e4`
- `0x18000f744`
- `0x18000fb34`
- `0x180012830`

## string_xrefs

- `0x18000ea41`: `\nComsvcs.dll file version info: %s %s %s`

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
  StringCchPrintfW(&word_1800204D0, 0x400u, &Filename, v16, v17, v15);
  SafeAppend(&word_1800204D0, v12, v13, a3);
}

```

## disassembly

```asm
0x18000ea1c  push    rbx
0x18000ea1e  sub     rsp, 0E0h
0x18000ea25  mov     rax, cs:__security_cookie
0x18000ea2c  xor     rax, rsp
0x18000ea2f  mov     [rsp+0E8h+var_18], rax
0x18000ea37  mov     rbx, r8
0x18000ea3a  lea     rax, Filename
0x18000ea41  lea     r8, aComsvcsDllFile; "\r\nComsvcs.dll file version info: %s %"...
0x18000ea48  mov     ecx, 7FFFFFFEh
0x18000ea4d  mov     edx, 81h
0x18000ea52  xor     r10d, r10d
0x18000ea55  test    rcx, rcx
0x18000ea58  jz      short loc_18000EA79
0x18000ea5a  movzx   r9d, word ptr [r8]
0x18000ea5e  test    r9w, r9w
0x18000ea62  jz      short loc_18000EA79
0x18000ea64  mov     [rax], r9w
0x18000ea68  add     r8, 2
0x18000ea6c  add     rax, 2
0x18000ea70  dec     rcx
0x18000ea73  sub     rdx, 1
0x18000ea77  jnz     short loc_18000EA55
0x18000ea79  test    rdx, rdx
0x18000ea7c  lea     rcx, [rax-2]
0x18000ea80  lea     rdx, Filename; unsigned __int16 *
0x18000ea87  cmovnz  rcx, rax
0x18000ea8b  mov     [rcx], r10w
0x18000ea8f  mov     ecx, 3AFh; unsigned int
0x18000ea94  call    ?GetFormatString@@YAXIPEAG@Z; GetFormatString(uint,ushort *)
0x18000ea99  lea     rax, [rsp+0E8h+var_A8]
0x18000ea9e  mov     [rsp+0E8h+var_B8], rax; unsigned __int16 *
0x18000eaa3  lea     r8, [rsp+0E8h+var_98]; unsigned __int16 *
0x18000eaa8  lea     rax, [rsp+0E8h+var_88]
0x18000eaad  mov     [rsp+0E8h+var_C8], rax; unsigned __int16 *
0x18000eab2  call    ?GetLoadedDllFileVersion@@YAXPEAGK0K0K0@Z; GetLoadedDllFileVersion(ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *)
0x18000eab7  lea     rax, [rsp+0E8h+var_A8]
0x18000eabc  mov     edx, 400h; unsigned __int64
0x18000eac1  mov     [rsp+0E8h+var_C0], rax
0x18000eac6  lea     r9, [rsp+0E8h+var_98]
0x18000eacb  lea     rax, [rsp+0E8h+var_88]
0x18000ead0  lea     r8, Filename; unsigned __int16 *
0x18000ead7  mov     [rsp+0E8h+var_C8], rax
0x18000eadc  lea     rcx, word_1800204D0; unsigned __int16 *
0x18000eae3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000eae8  mov     r9, rbx; unsigned int *
0x18000eaeb  lea     rcx, word_1800204D0; unsigned __int16 *
0x18000eaf2  call    ?SafeAppend@@YAXPEAGK0PEAI@Z; SafeAppend(ushort *,ulong,ushort *,uint *)
0x18000eaf7  mov     rcx, [rsp+0E8h+var_18]
0x18000eaff  xor     rcx, rsp; StackCookie
0x18000eb02  call    __security_check_cookie
0x18000eb07  add     rsp, 0E0h
0x18000eb0e  pop     rbx
0x18000eb0f  retn
```
