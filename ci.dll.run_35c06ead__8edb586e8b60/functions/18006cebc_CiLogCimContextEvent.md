# CiLogCimContextEvent

- ea: `0x18006cebc`
- end: `0x18006d025`
- name: `CiLogCimContextEvent`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d450`

## callees

- `0x18002c0d0`
- `0x18006cebc`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x18006cfcf`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006cfcf`
- `ntoskrnl!EtwWrite` at `0x18006cffb`
- `ntoskrnl!EtwWrite` at `0x18006cffb`

## pseudocode

```c
NTSTATUS __fastcall CiLogCimContextEvent(__int64 a1, unsigned __int16 *a2)
{
  __int64 *v2; // r8
  int v3; // r11d
  const wchar_t *v5; // rdx
  const wchar_t *v6; // r9
  int v7; // ecx
  int v8; // ecx
  __int64 v9; // rcx
  const GUID *ActivityIdThread; // rax
  __int16 v12; // [rsp+30h] [rbp-59h] BYREF
  __int16 v13; // [rsp+34h] [rbp-55h] BYREF
  __int16 v14; // [rsp+38h] [rbp-51h] BYREF
  int v15; // [rsp+3Ch] [rbp-4Dh] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-49h] BYREF
  __int64 v17; // [rsp+50h] [rbp-39h]
  int v18; // [rsp+58h] [rbp-31h]
  int v19; // [rsp+5Ch] [rbp-2Dh]
  int *v20; // [rsp+60h] [rbp-29h]
  __int64 v21; // [rsp+68h] [rbp-21h]
  __int64 v22; // [rsp+70h] [rbp-19h]
  int v23; // [rsp+78h] [rbp-11h]
  int v24; // [rsp+7Ch] [rbp-Dh]
  __int16 *v25; // [rsp+80h] [rbp-9h]
  __int64 v26; // [rsp+88h] [rbp-1h]
  __int64 v27; // [rsp+90h] [rbp+7h]
  int v28; // [rsp+98h] [rbp+Fh]
  int v29; // [rsp+9Ch] [rbp+13h]
  __int16 *v30; // [rsp+A0h] [rbp+17h]
  __int64 v31; // [rsp+A8h] [rbp+1Fh]
  __int64 v32; // [rsp+B0h] [rbp+27h]
  int v33; // [rsp+B8h] [rbp+2Fh]
  int v34; // [rsp+BCh] [rbp+33h]
  __int64 *v35; // [rsp+C0h] [rbp+37h]
  __int64 v36; // [rsp+C8h] [rbp+3Fh]

  v2 = *(__int64 **)(a1 + 2320);
  v3 = *a2;
  v15 = 0;
  v5 = L"\b\n";
  v12 = 0;
  v6 = (const wchar_t *)(v2 + 9);
  v13 = 0;
  v14 = 0;
  v7 = *((_DWORD *)v2 + 2);
  v15 = v7;
  v12 = (unsigned __int16)v3 >> 1;
  if ( !v2[10] )
    v6 = L"\b\n";
  if ( v2[12] )
    v5 = (const wchar_t *)(v2 + 11);
  v13 = *v6 >> 1;
  v14 = *v5 >> 1;
  UserData.Ptr = (ULONGLONG)&v12;
  v17 = *((_QWORD *)a2 + 1);
  v20 = &v15;
  *(_QWORD *)&UserData.Size = 2;
  v18 = v3;
  v19 = 0;
  v21 = 4;
  v22 = *v2;
  v25 = &v13;
  v23 = v7;
  v24 = 0;
  v26 = 2;
  v8 = *v6;
  v27 = *((_QWORD *)v6 + 1);
  v30 = &v14;
  v28 = v8;
  v29 = 0;
  v31 = 2;
  v9 = *v5;
  v32 = *((_QWORD *)v5 + 1);
  v35 = v2 + 13;
  v33 = v9;
  v34 = 0;
  v36 = 8;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread(v9);
  return EtwWrite(g_EtwEventHandle, &CiCimContextEvent, ActivityIdThread, 9u, &UserData);
}

```

## disassembly

```asm
0x18006cebc  mov     [rsp-8+arg_0], rdi
0x18006cec1  push    rbp
0x18006cec2  lea     rbp, [rsp-57h]
0x18006cec7  sub     rsp, 0E0h
0x18006cece  mov     rax, cs:__security_cookie
0x18006ced5  xor     rax, rsp
0x18006ced8  mov     [rbp+57h+var_10], rax
0x18006cedc  mov     r8, [rcx+910h]
0x18006cee3  xor     edi, edi
0x18006cee5  movzx   r11d, word ptr [rdx]
0x18006cee9  mov     r10, rdx
0x18006ceec  mov     [rbp+57h+var_A4], edi
0x18006ceef  lea     rdx, asc_180030780; "\b\n"
0x18006cef6  mov     [rbp+57h+var_B0], di
0x18006cefa  movzx   eax, r11w
0x18006cefe  shr     ax, 1
0x18006cf01  lea     r9, [r8+48h]
0x18006cf05  mov     [rbp+57h+var_AC], di
0x18006cf09  mov     [rbp+57h+var_A8], di
0x18006cf0d  mov     ecx, [r8+8]
0x18006cf11  mov     [rbp+57h+var_A4], ecx
0x18006cf14  mov     [rbp+57h+var_B0], ax
0x18006cf18  cmp     [r8+50h], rdi
0x18006cf1c  jnz     short loc_18006CF21
0x18006cf1e  mov     r9, rdx
0x18006cf21  cmp     [r8+60h], rdi
0x18006cf25  jz      short loc_18006CF2B
0x18006cf27  lea     rdx, [r8+58h]
0x18006cf2b  movzx   eax, word ptr [r9]
0x18006cf2f  shr     ax, 1
0x18006cf32  mov     [rbp+57h+var_AC], ax
0x18006cf36  movzx   eax, word ptr [rdx]
0x18006cf39  shr     ax, 1
0x18006cf3c  mov     [rbp+57h+var_A8], ax
0x18006cf40  lea     rax, [rbp+57h+var_B0]
0x18006cf44  mov     [rbp+57h+var_A0.Ptr], rax
0x18006cf48  mov     rax, [r10+8]
0x18006cf4c  mov     [rbp+57h+var_90], rax
0x18006cf50  lea     rax, [rbp+57h+var_A4]
0x18006cf54  mov     [rbp+57h+var_80], rax
0x18006cf58  mov     qword ptr [rbp+57h+var_A0.Size], 2
0x18006cf60  mov     [rbp+57h+var_88], r11d
0x18006cf64  mov     [rbp+57h+var_84], edi
0x18006cf67  mov     [rbp+57h+var_78], 4
0x18006cf6f  mov     rax, [r8]
0x18006cf72  mov     [rbp+57h+var_70], rax
0x18006cf76  lea     rax, [rbp+57h+var_AC]
0x18006cf7a  mov     [rbp+57h+var_60], rax
0x18006cf7e  mov     [rbp+57h+var_68], ecx
0x18006cf81  mov     [rbp+57h+var_64], edi
0x18006cf84  mov     [rbp+57h+var_58], 2
0x18006cf8c  mov     rax, [r9+8]
0x18006cf90  movzx   ecx, word ptr [r9]
0x18006cf94  mov     [rbp+57h+var_50], rax
0x18006cf98  lea     rax, [rbp+57h+var_A8]
0x18006cf9c  mov     [rbp+57h+var_40], rax
0x18006cfa0  mov     [rbp+57h+var_48], ecx
0x18006cfa3  mov     [rbp+57h+var_44], edi
0x18006cfa6  mov     [rbp+57h+var_38], 2
0x18006cfae  mov     rax, [rdx+8]
0x18006cfb2  movzx   ecx, word ptr [rdx]
0x18006cfb5  mov     [rbp+57h+var_30], rax
0x18006cfb9  lea     rax, [r8+68h]
0x18006cfbd  mov     [rbp+57h+var_20], rax
0x18006cfc1  mov     [rbp+57h+var_28], ecx
0x18006cfc4  mov     [rbp+57h+var_24], edi
0x18006cfc7  mov     [rbp+57h+var_18], 8
0x18006cfcf  call    cs:__imp_IoGetActivityIdThread
0x18006cfd6  nop     dword ptr [rax+rax+00h]
0x18006cfdb  lea     rcx, [rbp+57h+var_A0]
0x18006cfdf  mov     r9d, 9; UserDataCount
0x18006cfe5  mov     [rsp+0E0h+UserData], rcx; UserData
0x18006cfea  lea     rdx, CiCimContextEvent; EventDescriptor
0x18006cff1  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006cff8  mov     r8, rax; ActivityId
0x18006cffb  call    cs:__imp_EtwWrite
0x18006d002  nop     dword ptr [rax+rax+00h]
0x18006d007  mov     rcx, [rbp+57h+var_10]
0x18006d00b  xor     rcx, rsp; StackCookie
0x18006d00e  call    __security_check_cookie
0x18006d013  mov     rdi, [rsp+0E0h+arg_0]
0x18006d01b  add     rsp, 0E0h
0x18006d022  pop     rbp
0x18006d023  retn
```
