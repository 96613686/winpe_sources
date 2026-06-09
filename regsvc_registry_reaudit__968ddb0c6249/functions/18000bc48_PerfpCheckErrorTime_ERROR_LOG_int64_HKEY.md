# PerfpCheckErrorTime(ERROR_LOG *,__int64,HKEY__ *)

- ea: `0x18000bc48`
- end: `0x18000be08`
- name: `?PerfpCheckErrorTime@@YAKPEAUERROR_LOG@@_JPEAUHKEY__@@@Z`
- size: `448`
- prototype: `unsigned int(struct ERROR_LOG *, __int64, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c134`

## callees

- `0x180007740`
- `0x18000bc48`
- `0x18000c2b0`
- `0x18000c7ec`
- `0x18000c878`

## import_xrefs

- `ntdll!RtlIntegerToUnicodeString` at `0x18000bd10`
- `ntdll!RtlIntegerToUnicodeString` at `0x18000bd10`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bdc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bdc6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bc87`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bc87`

## pseudocode

```c
__int64 __fastcall PerfpCheckErrorTime(struct ERROR_LOG *a1, __int64 a2, HKEY a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  struct _FILETIME v7; // rcx
  unsigned __int8 *p_el_text; // rbx
  unsigned int v10; // esi
  ULONG el_name; // ecx
  int v12; // edx
  unsigned int *v13; // r8
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v15; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v16; // [rsp+4Ch] [rbp-2Dh] BYREF
  struct _UNICODE_STRING String; // [rsp+50h] [rbp-29h] BYREF
  WCHAR ValueName[32]; // [rsp+60h] [rbp-19h] BYREF

  SystemTimeAsFileTime = 0;
  String = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_diii)(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      v6,
      LODWORD(a1->el_name),
      SystemTimeAsFileTime,
      a1->el_text);
  v7 = SystemTimeAsFileTime;
  p_el_text = (unsigned __int8 *)&a1->el_text;
  if ( (__int64)(*(_QWORD *)&SystemTimeAsFileTime - (unsigned __int64)a1->el_text) < 864000000000LL )
    return 0;
  v10 = 0;
  ValueName[0] = 0;
  if ( a3 )
  {
    el_name = (ULONG)a1->el_name;
    String.Buffer = ValueName;
    *(_DWORD *)&String.Length = 0x400000;
    RtlIntegerToUnicodeString(el_name, 0xAu, &String);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, (_DWORD)v13, a1->el_name, (__int64)String.Buffer);
    if ( *(_QWORD *)p_el_text
      || (v15 = 4, v16 = 8, (unsigned int)PrivateRegQueryValueExT(a3, ValueName, v13, &v15, p_el_text, &v16, 1))
      || v15 != 11 )
    {
      v7 = SystemTimeAsFileTime;
    }
    else
    {
      v7 = SystemTimeAsFileTime;
      if ( (__int64)(*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)p_el_text) >= 864000000000LL )
        *(_QWORD *)p_el_text = 0;
    }
    if ( !*(_QWORD *)p_el_text )
    {
      *(struct _FILETIME *)p_el_text = v7;
      v10 = 1;
      RegSetValueExW(a3, ValueName, 0, 0xBu, (const BYTE *)&SystemTimeAsFileTime, 8u);
      v7 = SystemTimeAsFileTime;
    }
  }
  if ( (__int64)(*(_QWORD *)&v7 - *(_QWORD *)p_el_text) >= 864000000000LL )
  {
    *(struct _FILETIME *)p_el_text = v7;
    return 1;
  }
  return v10;
}

```

## disassembly

```asm
0x18000bc48  mov     [rsp-8+arg_8], rbx
0x18000bc4d  push    rbp
0x18000bc4e  push    rsi
0x18000bc4f  push    rdi
0x18000bc50  push    r12
0x18000bc52  push    r14
0x18000bc54  lea     rbp, [rsp-37h]
0x18000bc59  sub     rsp, 0B0h
0x18000bc60  mov     rax, cs:__security_cookie
0x18000bc67  xor     rax, rsp
0x18000bc6a  mov     [rbp+57h+var_30], rax
0x18000bc6e  mov     rdi, rcx
0x18000bc71  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000bc79  xorps   xmm0, xmm0
0x18000bc7c  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000bc80  movups  xmmword ptr [rbp+57h+String.Length], xmm0
0x18000bc84  mov     r14, r8
0x18000bc87  call    cs:__imp_GetSystemTimeAsFileTime
0x18000bc8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc94  test    dword ptr [rcx+1Ch], 800h
0x18000bc9b  jz      short loc_18000BCC2
0x18000bc9d  cmp     byte ptr [rcx+19h], 4
0x18000bca1  jb      short loc_18000BCC2
0x18000bca3  mov     rax, [rdi+18h]
0x18000bca7  mov     r9d, [rdi+10h]
0x18000bcab  mov     rcx, [rcx+10h]
0x18000bcaf  mov     qword ptr [rsp+0D0h+cbData], rax
0x18000bcb4  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18000bcb8  mov     [rsp+0D0h+lpData], rax
0x18000bcbd  call    WPP_SF_diii
0x18000bcc2  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18000bcc6  lea     rbx, [rdi+18h]
0x18000bcca  mov     rax, rcx
0x18000bccd  mov     r12, 0C92A69C000h
0x18000bcd7  sub     rax, [rbx]
0x18000bcda  cmp     rax, r12
0x18000bcdd  jge     short loc_18000BCE6
0x18000bcdf  xor     eax, eax
0x18000bce1  jmp     loc_18000BDE5
0x18000bce6  xor     eax, eax
0x18000bce8  xor     esi, esi
0x18000bcea  mov     [rbp+57h+ValueName], ax
0x18000bcee  test    r14, r14
0x18000bcf1  jz      loc_18000BDD0
0x18000bcf7  mov     ecx, [rdi+10h]; Value
0x18000bcfa  lea     rax, [rbp+57h+ValueName]
0x18000bcfe  lea     r8, [rbp+57h+String]; String
0x18000bd02  mov     [rbp+57h+String.Buffer], rax
0x18000bd06  lea     edx, [rsi+0Ah]; Base
0x18000bd09  mov     dword ptr [rbp+57h+String.Length], 400000h
0x18000bd10  call    cs:__imp_RtlIntegerToUnicodeString
0x18000bd16  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd1d  test    dword ptr [rcx+1Ch], 800h
0x18000bd24  jz      short loc_18000BD42
0x18000bd26  cmp     byte ptr [rcx+19h], 4
0x18000bd2a  jb      short loc_18000BD42
0x18000bd2c  mov     rax, [rbp+57h+String.Buffer]
0x18000bd30  mov     r9d, [rdi+10h]
0x18000bd34  mov     rcx, [rcx+10h]
0x18000bd38  mov     [rsp+0D0h+lpData], rax
0x18000bd3d  call    WPP_SF_dS
0x18000bd42  mov     edi, 8
0x18000bd47  cmp     [rbx], rsi
0x18000bd4a  jnz     short loc_18000BD9A
0x18000bd4c  lea     rax, [rbp+57h+var_84]
0x18000bd50  mov     [rsp+0D0h+var_A0], 1; int
0x18000bd58  mov     qword ptr [rsp+0D0h+cbData], rax; unsigned int *
0x18000bd5d  lea     r9, [rbp+57h+var_88]; unsigned int *
0x18000bd61  lea     rdx, [rbp+57h+ValueName]; unsigned __int16 *
0x18000bd65  mov     [rsp+0D0h+lpData], rbx; unsigned __int8 *
0x18000bd6a  mov     rcx, r14; KeyHandle
0x18000bd6d  mov     [rbp+57h+var_88], 4
0x18000bd74  mov     [rbp+57h+var_84], edi
0x18000bd77  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x18000bd7c  test    eax, eax
0x18000bd7e  jnz     short loc_18000BD9A
0x18000bd80  cmp     [rbp+57h+var_88], 0Bh
0x18000bd84  jnz     short loc_18000BD9A
0x18000bd86  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18000bd8a  mov     rax, rcx
0x18000bd8d  sub     rax, [rbx]
0x18000bd90  cmp     rax, r12
0x18000bd93  jl      short loc_18000BD9E
0x18000bd95  mov     [rbx], rsi
0x18000bd98  jmp     short loc_18000BD9E
0x18000bd9a  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18000bd9e  cmp     [rbx], rsi
0x18000bda1  jnz     short loc_18000BDD0
0x18000bda3  mov     [rbx], rcx
0x18000bda6  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x18000bdaa  mov     esi, 1
0x18000bdaf  mov     [rsp+0D0h+cbData], edi; cbData
0x18000bdb3  xor     r8d, r8d; Reserved
0x18000bdb6  mov     [rsp+0D0h+lpData], rax; lpData
0x18000bdbb  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x18000bdbf  mov     rcx, r14; hKey
0x18000bdc2  lea     r9d, [rsi+0Ah]; dwType
0x18000bdc6  call    cs:__imp_RegSetValueExW
0x18000bdcc  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18000bdd0  mov     rax, rcx
0x18000bdd3  sub     rax, [rbx]
0x18000bdd6  cmp     rax, r12
0x18000bdd9  jl      short loc_18000BDE3
0x18000bddb  mov     [rbx], rcx
0x18000bdde  mov     esi, 1
0x18000bde3  mov     eax, esi
0x18000bde5  mov     rcx, [rbp+57h+var_30]
0x18000bde9  xor     rcx, rsp; StackCookie
0x18000bdec  call    __security_check_cookie
0x18000bdf1  mov     rbx, [rsp+0D0h+arg_8]
0x18000bdf9  add     rsp, 0B0h
0x18000be00  pop     r14
0x18000be02  pop     r12
0x18000be04  pop     rdi
0x18000be05  pop     rsi
0x18000be06  pop     rbp
0x18000be07  retn
```
