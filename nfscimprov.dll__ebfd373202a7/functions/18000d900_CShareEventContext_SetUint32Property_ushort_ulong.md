# CShareEventContext::SetUint32Property(ushort *,ulong)

- ea: `0x18000d900`
- end: `0x18000dad1`
- name: `?SetUint32Property@CShareEventContext@@QEAAXPEAGK@Z`
- size: `465`
- prototype: `void __fastcall(CShareEventContext *__hidden this, wchar_t *String1, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d5e0`
- `0x18000dae0`

## callees

- `0x18000bda0`
- `0x18000bf04`
- `0x18000d900`
- `0x180035b40`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d950`
- `msvcrt!_wcsicmp` at `0x18000d9d7`
- `msvcrt!_wcsicmp` at `0x18000d9fd`
- `msvcrt!_wcsicmp` at `0x18000da23`
- `msvcrt!_wcsicmp` at `0x18000d950`
- `msvcrt!_wcsicmp` at `0x18000d9d7`
- `msvcrt!_wcsicmp` at `0x18000d9fd`
- `msvcrt!_wcsicmp` at `0x18000da23`

## string_xrefs

- `0x18000da19`: `SecurityFlavorsFlags`

## pseudocode

```c
void __fastcall CShareEventContext::SetUint32Property(CShareEventContext *this, wchar_t *String1, int a3)
{
  bool v3; // zf
  int v7; // eax
  char v8; // cl
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rax
  _OWORD v12[3]; // [rsp+20h] [rbp-48h] BYREF

  v3 = *((_DWORD *)this + 88) == -1;
  memset(v12, 0, sizeof(v12));
  if ( !v3 )
  {
    if ( !_wcsicmp(String1, L"ShareFlags") )
    {
      *((_BYTE *)this + 273) = 1;
      *((_BYTE *)this + 272) = (a3 & 0x800000) != 0;
      *((_BYTE *)this + 345) = 1;
      *((_BYTE *)this + 344) = (a3 & 0x3000000) != 0;
      v7 = a3 & 0x10000;
      *(_WORD *)((char *)this + 275) = 257;
      if ( (a3 & 0x400000) != 0 )
      {
        if ( !v7 )
        {
          LOBYTE(v7) = 0;
          v8 = 1;
          goto LABEL_10;
        }
      }
      else if ( !v7 )
      {
        goto LABEL_8;
      }
      LOBYTE(v7) = 1;
LABEL_8:
      v8 = 0;
LABEL_10:
      *((_BYTE *)this + 323) = v7;
      *((_BYTE *)this + 324) = 1;
      *((_BYTE *)this + 320) = v8;
      *((_BYTE *)this + 321) = 1;
      return;
    }
    if ( _wcsicmp(String1, L"UnmappedUid") )
    {
      if ( _wcsicmp(String1, L"UnmappedGid") )
      {
        if ( !_wcsicmp(String1, L"SecurityFlavorsFlags") )
        {
          if ( (a3 & 2) != 0 )
            *(_QWORD *)&v12[0] = L"sys";
          v9 = (a3 & 2) != 0;
          if ( (a3 & 4) != 0 )
          {
            v9 = (unsigned int)(v9 + 1);
            *((_QWORD *)v12 + ((a3 & 2) != 0)) = L"Krb5";
          }
          if ( (a3 & 8) != 0 )
          {
            v10 = (unsigned int)v9;
            v9 = (unsigned int)(v9 + 1);
            *((_QWORD *)v12 + v10) = L"Krb5i";
          }
          if ( (a3 & 0x10) != 0 )
          {
            v11 = (unsigned int)v9;
            v9 = (unsigned int)(v9 + 1);
            *((_QWORD *)v12 + v11) = L"Krb5p";
          }
          if ( (unsigned int)MSFT_NfsShare_Set_Authentication((char *)this + 176, v12, v9) )
            CShareEventContext::Invalidate(this);
        }
      }
      else
      {
        *((_DWORD *)this + 84) = a3;
        *((_BYTE *)this + 340) = 1;
      }
    }
    else
    {
      *((_DWORD *)this + 82) = a3;
      *((_BYTE *)this + 332) = 1;
    }
  }
}

```

## disassembly

```asm
0x18000d900  mov     [rsp+arg_10], rbx
0x18000d905  mov     [rsp+arg_18], rsi
0x18000d90a  push    rdi
0x18000d90b  sub     rsp, 60h
0x18000d90f  mov     rax, cs:__security_cookie
0x18000d916  xor     rax, rsp
0x18000d919  mov     [rsp+68h+var_18], rax
0x18000d91e  cmp     dword ptr [rcx+160h], 0FFFFFFFFh
0x18000d925  xorps   xmm0, xmm0
0x18000d928  movups  [rsp+68h+var_48], xmm0
0x18000d92d  mov     edi, r8d
0x18000d930  mov     rsi, rdx
0x18000d933  movups  [rsp+68h+var_38], xmm0
0x18000d938  mov     rbx, rcx
0x18000d93b  movups  [rsp+68h+var_28], xmm0
0x18000d940  jz      loc_18000DAB2
0x18000d946  lea     rdx, aShareflags; "ShareFlags"
0x18000d94d  mov     rcx, rsi; String1
0x18000d950  call    cs:__imp__wcsicmp
0x18000d956  test    eax, eax
0x18000d958  jnz     short loc_18000D9CD
0x18000d95a  mov     byte ptr [rbx+111h], 1
0x18000d961  mov     eax, edi
0x18000d963  shr     eax, 17h
0x18000d966  and     al, 1
0x18000d968  mov     [rbx+110h], al
0x18000d96e  test    edi, 3000000h
0x18000d974  mov     byte ptr [rbx+159h], 1
0x18000d97b  setnz   al
0x18000d97e  mov     [rbx+158h], al
0x18000d984  mov     eax, edi
0x18000d986  and     eax, 10000h
0x18000d98b  mov     word ptr [rbx+113h], 101h
0x18000d994  bt      edi, 16h
0x18000d998  jb      short loc_18000D9A0
0x18000d99a  test    eax, eax
0x18000d99c  jnz     short loc_18000D9A4
0x18000d99e  jmp     short loc_18000D9A6
0x18000d9a0  test    eax, eax
0x18000d9a2  jz      short loc_18000D9AA
0x18000d9a4  mov     al, 1
0x18000d9a6  xor     cl, cl
0x18000d9a8  jmp     short loc_18000D9AE
0x18000d9aa  xor     al, al
0x18000d9ac  mov     cl, 1
0x18000d9ae  mov     [rbx+143h], al
0x18000d9b4  mov     byte ptr [rbx+144h], 1
0x18000d9bb  mov     [rbx+140h], cl
0x18000d9c1  mov     byte ptr [rbx+141h], 1
0x18000d9c8  jmp     loc_18000DAB2
0x18000d9cd  lea     rdx, aUnmappeduid_0; "UnmappedUid"
0x18000d9d4  mov     rcx, rsi; String1
0x18000d9d7  call    cs:__imp__wcsicmp
0x18000d9dd  test    eax, eax
0x18000d9df  jnz     short loc_18000D9F3
0x18000d9e1  mov     [rbx+148h], edi
0x18000d9e7  mov     byte ptr [rbx+14Ch], 1
0x18000d9ee  jmp     loc_18000DAB2
0x18000d9f3  lea     rdx, aUnmappedgid; "UnmappedGid"
0x18000d9fa  mov     rcx, rsi; String1
0x18000d9fd  call    cs:__imp__wcsicmp
0x18000da03  test    eax, eax
0x18000da05  jnz     short loc_18000DA19
0x18000da07  mov     [rbx+150h], edi
0x18000da0d  mov     byte ptr [rbx+154h], 1
0x18000da14  jmp     loc_18000DAB2
0x18000da19  lea     rdx, aSecurityflavor; "SecurityFlavorsFlags"
0x18000da20  mov     rcx, rsi; String1
0x18000da23  call    cs:__imp__wcsicmp
0x18000da29  test    eax, eax
0x18000da2b  jnz     loc_18000DAB2
0x18000da31  mov     eax, edi
0x18000da33  and     eax, 2
0x18000da36  jz      short loc_18000DA44
0x18000da38  lea     rcx, aSys; "sys"
0x18000da3f  mov     qword ptr [rsp+68h+var_48], rcx
0x18000da44  xor     r8d, r8d
0x18000da47  test    eax, eax
0x18000da49  setnz   r8b
0x18000da4d  test    dil, 4
0x18000da51  jz      short loc_18000DA65
0x18000da53  mov     eax, r8d
0x18000da56  lea     rcx, aKrb5; "Krb5"
0x18000da5d  inc     r8d
0x18000da60  mov     qword ptr [rsp+rax*8+68h+var_48], rcx
0x18000da65  test    dil, 8
0x18000da69  jz      short loc_18000DA7D
0x18000da6b  mov     eax, r8d
0x18000da6e  lea     rcx, aKrb5i; "Krb5i"
0x18000da75  inc     r8d
0x18000da78  mov     qword ptr [rsp+rax*8+68h+var_48], rcx
0x18000da7d  test    dil, 10h
0x18000da81  jz      short loc_18000DA95
0x18000da83  mov     eax, r8d
0x18000da86  lea     rcx, aKrb5p; "Krb5p"
0x18000da8d  inc     r8d
0x18000da90  mov     qword ptr [rsp+rax*8+68h+var_48], rcx
0x18000da95  lea     rcx, [rbx+0B0h]
0x18000da9c  lea     rdx, [rsp+68h+var_48]
0x18000daa1  call    MSFT_NfsShare_Set_Authentication
0x18000daa6  test    eax, eax
0x18000daa8  jz      short loc_18000DAB2
0x18000daaa  mov     rcx, rbx; this
0x18000daad  call    ?Invalidate@CShareEventContext@@AEAAXXZ; CShareEventContext::Invalidate(void)
0x18000dab2  mov     rcx, [rsp+68h+var_18]
0x18000dab7  xor     rcx, rsp; StackCookie
0x18000daba  call    __security_check_cookie
0x18000dabf  lea     r11, [rsp+68h+var_8]
0x18000dac4  mov     rbx, [r11+20h]
0x18000dac8  mov     rsi, [r11+28h]
0x18000dacc  mov     rsp, r11
0x18000dacf  pop     rdi
0x18000dad0  retn
```
