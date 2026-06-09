# OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x180003894`
- end: `0x1800039bf`
- name: `?GetCredentialsForBasicProxyIfPresent@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAG_K12@Z`
- size: `299`
- prototype: `int(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000354c`
- `0x180007170`

## callees

- `0x180003894`
- `0x180007ae0`

## import_xrefs

- `ADVAPI32!CredFree` at `0x1800039a7`
- `ADVAPI32!CredFree` at `0x1800039a7`
- `ADVAPI32!CredReadW` at `0x1800038be`
- `ADVAPI32!CredReadW` at `0x1800038be`
- `KERNEL32!GetLastError` at `0x1800038c8`
- `KERNEL32!GetLastError` at `0x1800038c8`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5)
{
  signed int LastError; // eax
  signed int v7; // ebx
  const unsigned __int16 **v8; // rdx
  unsigned __int16 *v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int16 *v11; // r9
  __int64 v12; // r8
  unsigned __int16 *v13; // rcx
  int v14; // eax
  PVOID Buffer; // [rsp+48h] [rbp+20h] BYREF

  Buffer = 0;
  if ( CredReadW(a2, 1u, 0, (PCREDENTIALW *)&Buffer) )
  {
    v8 = (const unsigned __int16 **)Buffer;
    v9 = (unsigned __int16 *)*((_QWORD *)Buffer + 5);
    if ( v9 && *((_QWORD *)Buffer + 9) )
    {
      v10 = (unsigned __int64)*((unsigned int *)Buffer + 8) >> 1;
      if ( v10 <= 0x7FFFFFFE )
      {
        v11 = a5;
        v12 = 260;
        do
        {
          if ( !v10 )
            break;
          if ( !*v9 )
            break;
          *v11++ = *v9++;
          --v10;
          --v12;
        }
        while ( v12 );
        v13 = v11 - 1;
        v7 = v12 == 0 ? 0x8007007A : 0;
        if ( v12 )
          v13 = v11;
        *v13 = 0;
        if ( v12 )
        {
          v14 = StringCchCopyW(a3, 0x104u, v8[9]);
          v8 = (const unsigned __int16 **)Buffer;
          v7 = v14;
          if ( v14 >= 0 )
            v7 = 0;
        }
      }
      else
      {
        v7 = -2147024809;
        *a5 = 0;
      }
    }
    else
    {
      v7 = -2147467259;
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = (const unsigned __int16 **)Buffer;
    if ( v7 >= 0 )
      v7 = -2147467259;
  }
  if ( v8 )
    CredFree(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003894  mov     rax, rsp
0x180003897  mov     [rax+8], rbx
0x18000389b  mov     [rax+10h], rsi
0x18000389f  mov     [rax+20h], r9
0x1800038a3  push    rdi
0x1800038a4  sub     rsp, 20h
0x1800038a8  xor     esi, esi
0x1800038aa  lea     r9, [rax+20h]; Credential
0x1800038ae  mov     rdi, r8
0x1800038b1  mov     [rax+20h], rsi
0x1800038b5  mov     rcx, rdx; TargetName
0x1800038b8  xor     r8d, r8d; Flags
0x1800038bb  lea     edx, [rsi+1]; Type
0x1800038be  call    cs:__imp_CredReadW
0x1800038c4  test    eax, eax
0x1800038c6  jnz     short loc_1800038F1
0x1800038c8  call    cs:__imp_GetLastError
0x1800038ce  mov     ebx, eax
0x1800038d0  test    eax, eax
0x1800038d2  jle     short loc_1800038DD
0x1800038d4  movzx   ebx, ax
0x1800038d7  or      ebx, 80070000h
0x1800038dd  mov     rdx, [rsp+28h+Buffer]
0x1800038e2  test    ebx, ebx
0x1800038e4  mov     eax, 80004005h
0x1800038e9  cmovns  ebx, eax
0x1800038ec  jmp     loc_18000399F
0x1800038f1  mov     rdx, [rsp+28h+Buffer]
0x1800038f6  mov     rcx, [rdx+28h]
0x1800038fa  test    rcx, rcx
0x1800038fd  jz      loc_18000399A
0x180003903  cmp     [rdx+48h], rsi
0x180003907  jz      loc_18000399A
0x18000390d  mov     eax, [rdx+20h]
0x180003910  shr     rax, 1
0x180003913  cmp     rax, 7FFFFFFEh
0x180003919  jbe     short loc_18000392A
0x18000391b  mov     rax, [rsp+28h+arg_20]
0x180003920  mov     ebx, 80070057h
0x180003925  mov     [rax], si
0x180003928  jmp     short loc_18000399F
0x18000392a  mov     r9, [rsp+28h+arg_20]
0x18000392f  mov     r11d, 104h
0x180003935  mov     r8d, r11d
0x180003938  test    rax, rax
0x18000393b  jz      short loc_18000395C
0x18000393d  movzx   r10d, word ptr [rcx]
0x180003941  test    r10w, r10w
0x180003945  jz      short loc_18000395C
0x180003947  mov     [r9], r10w
0x18000394b  add     rcx, 2
0x18000394f  add     r9, 2
0x180003953  dec     rax
0x180003956  sub     r8, 1
0x18000395a  jnz     short loc_180003938
0x18000395c  mov     rax, r8
0x18000395f  lea     rcx, [r9-2]
0x180003963  neg     rax
0x180003966  sbb     ebx, ebx
0x180003968  not     ebx
0x18000396a  and     ebx, 8007007Ah
0x180003970  test    r8, r8
0x180003973  cmovnz  rcx, r9
0x180003977  mov     [rcx], si
0x18000397a  jz      short loc_18000399F
0x18000397c  mov     r8, [rdx+48h]; unsigned __int16 *
0x180003980  mov     rcx, rdi; unsigned __int16 *
0x180003983  mov     rdx, r11; unsigned __int64
0x180003986  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000398b  mov     rdx, [rsp+28h+Buffer]
0x180003990  mov     ebx, eax
0x180003992  test    eax, eax
0x180003994  js      short loc_18000399F
0x180003996  mov     ebx, esi
0x180003998  jmp     short loc_18000399F
0x18000399a  mov     ebx, 80004005h
0x18000399f  test    rdx, rdx
0x1800039a2  jz      short loc_1800039AD
0x1800039a4  mov     rcx, rdx; Buffer
0x1800039a7  call    cs:__imp_CredFree
0x1800039ad  mov     rsi, [rsp+28h+arg_8]
0x1800039b2  mov     eax, ebx
0x1800039b4  mov     rbx, [rsp+28h+arg_0]
0x1800039b9  add     rsp, 20h
0x1800039bd  pop     rdi
0x1800039be  retn
```
