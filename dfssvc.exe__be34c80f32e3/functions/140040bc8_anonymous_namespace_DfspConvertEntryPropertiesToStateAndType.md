# _anonymous_namespace_::DfspConvertEntryPropertiesToStateAndType

- ea: `0x140040bc8`
- end: `0x140040d55`
- name: `_anonymous_namespace_::DfspConvertEntryPropertiesToStateAndType`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400413a8`

## callees

- `0x140040bc8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140040c09`
- `msvcrt!_wcsicmp` at `0x140040c2b`
- `msvcrt!_wcsicmp` at `0x140040c4d`
- `msvcrt!_wcsicmp` at `0x140040c6f`
- `msvcrt!_wcsicmp` at `0x140040c91`
- `msvcrt!_wcsicmp` at `0x140040cb0`
- `msvcrt!_wcsicmp` at `0x140040ccf`
- `msvcrt!_wcsicmp` at `0x140040cef`
- `msvcrt!_wcsicmp` at `0x140040d0f`
- `msvcrt!_wcsicmp` at `0x140040c09`
- `msvcrt!_wcsicmp` at `0x140040c2b`
- `msvcrt!_wcsicmp` at `0x140040c4d`
- `msvcrt!_wcsicmp` at `0x140040c6f`
- `msvcrt!_wcsicmp` at `0x140040c91`
- `msvcrt!_wcsicmp` at `0x140040cb0`
- `msvcrt!_wcsicmp` at `0x140040ccf`
- `msvcrt!_wcsicmp` at `0x140040cef`
- `msvcrt!_wcsicmp` at `0x140040d0f`

## string_xrefs

- `0x140040c68`: `Interlink=on`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::DfspConvertEntryPropertiesToStateAndType(const wchar_t **a1, int *a2)
{
  const wchar_t *v2; // rax
  unsigned int v3; // ebx
  int v6; // esi
  __int64 v7; // rbp
  const wchar_t **v8; // rdi
  __int64 result; // rax

  v2 = *a1;
  v3 = 1;
  v6 = 4;
  if ( *a1 )
  {
    v7 = 0;
    v8 = a1;
    do
    {
      if ( _wcsicmp(L"State=online", v2) )
      {
        if ( _wcsicmp(L"State=offline", *v8) )
        {
          if ( _wcsicmp(L"State=okay", *v8) )
          {
            if ( _wcsicmp(L"Interlink=on", *v8) )
            {
              if ( _wcsicmp(L"InsiteReferral=on", *v8) )
              {
                if ( _wcsicmp(L"ReferralSiteCosting=on", *v8) )
                {
                  if ( _wcsicmp(L"RootScalability=on", *v8) )
                  {
                    if ( _wcsicmp(L"TargetFailback=on", *v8) )
                    {
                      if ( !_wcsicmp(L"ABDE=on", *v8) )
                        v3 |= 0x10000u;
                    }
                    else
                    {
                      v3 |= 0x8000u;
                    }
                  }
                  else
                  {
                    v3 |= 0x200u;
                  }
                }
                else
                {
                  v3 |= 0x40u;
                }
              }
              else
              {
                v3 |= 0x20u;
              }
            }
            else
            {
              v3 |= 0x10u;
            }
          }
          else
          {
            v6 = 1;
          }
        }
        else
        {
          v6 = 3;
        }
      }
      else
      {
        v6 = 4;
      }
      v8 = &a1[++v7];
      v2 = *v8;
    }
    while ( *v8 );
  }
  result = v3;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x140040bc8  mov     [rsp+arg_0], rbx
0x140040bcd  mov     [rsp+arg_8], rbp
0x140040bd2  mov     [rsp+arg_10], rsi
0x140040bd7  push    rdi
0x140040bd8  push    r14
0x140040bda  push    r15
0x140040bdc  sub     rsp, 20h
0x140040be0  mov     rax, [rcx]
0x140040be3  mov     ebx, 1
0x140040be8  mov     r15, rdx
0x140040beb  mov     r14, rcx
0x140040bee  lea     esi, [rbx+3]
0x140040bf1  test    rax, rax
0x140040bf4  jz      loc_140040D36
0x140040bfa  xor     ebp, ebp
0x140040bfc  mov     rdi, rcx
0x140040bff  mov     rdx, rax; String2
0x140040c02  lea     rcx, aStateOnline; "State=online"
0x140040c09  call    cs:__imp__wcsicmp
0x140040c10  nop     dword ptr [rax+rax+00h]
0x140040c15  test    eax, eax
0x140040c17  jnz     short loc_140040C21
0x140040c19  lea     esi, [rax+4]
0x140040c1c  jmp     loc_140040D23
0x140040c21  mov     rdx, [rdi]; String2
0x140040c24  lea     rcx, aStateOffline; "State=offline"
0x140040c2b  call    cs:__imp__wcsicmp
0x140040c32  nop     dword ptr [rax+rax+00h]
0x140040c37  test    eax, eax
0x140040c39  jnz     short loc_140040C43
0x140040c3b  lea     esi, [rax+3]
0x140040c3e  jmp     loc_140040D23
0x140040c43  mov     rdx, [rdi]; String2
0x140040c46  lea     rcx, aStateOkay; "State=okay"
0x140040c4d  call    cs:__imp__wcsicmp
0x140040c54  nop     dword ptr [rax+rax+00h]
0x140040c59  test    eax, eax
0x140040c5b  jnz     short loc_140040C65
0x140040c5d  lea     esi, [rax+1]
0x140040c60  jmp     loc_140040D23
0x140040c65  mov     rdx, [rdi]; String2
0x140040c68  lea     rcx, aInterlinkOn; "Interlink=on"
0x140040c6f  call    cs:__imp__wcsicmp
0x140040c76  nop     dword ptr [rax+rax+00h]
0x140040c7b  test    eax, eax
0x140040c7d  jnz     short loc_140040C87
0x140040c7f  or      ebx, 10h
0x140040c82  jmp     loc_140040D23
0x140040c87  mov     rdx, [rdi]; String2
0x140040c8a  lea     rcx, aInsitereferral; "InsiteReferral=on"
0x140040c91  call    cs:__imp__wcsicmp
0x140040c98  nop     dword ptr [rax+rax+00h]
0x140040c9d  test    eax, eax
0x140040c9f  jnz     short loc_140040CA6
0x140040ca1  or      ebx, 20h
0x140040ca4  jmp     short loc_140040D23
0x140040ca6  mov     rdx, [rdi]; String2
0x140040ca9  lea     rcx, aReferralsiteco; "ReferralSiteCosting=on"
0x140040cb0  call    cs:__imp__wcsicmp
0x140040cb7  nop     dword ptr [rax+rax+00h]
0x140040cbc  test    eax, eax
0x140040cbe  jnz     short loc_140040CC5
0x140040cc0  or      ebx, 40h
0x140040cc3  jmp     short loc_140040D23
0x140040cc5  mov     rdx, [rdi]; String2
0x140040cc8  lea     rcx, aRootscalabilit_0; "RootScalability=on"
0x140040ccf  call    cs:__imp__wcsicmp
0x140040cd6  nop     dword ptr [rax+rax+00h]
0x140040cdb  test    eax, eax
0x140040cdd  jnz     short loc_140040CE5
0x140040cdf  bts     ebx, 9
0x140040ce3  jmp     short loc_140040D23
0x140040ce5  mov     rdx, [rdi]; String2
0x140040ce8  lea     rcx, aTargetfailback; "TargetFailback=on"
0x140040cef  call    cs:__imp__wcsicmp
0x140040cf6  nop     dword ptr [rax+rax+00h]
0x140040cfb  test    eax, eax
0x140040cfd  jnz     short loc_140040D05
0x140040cff  bts     ebx, 0Fh
0x140040d03  jmp     short loc_140040D23
0x140040d05  mov     rdx, [rdi]; String2
0x140040d08  lea     rcx, aAbdeOn; "ABDE=on"
0x140040d0f  call    cs:__imp__wcsicmp
0x140040d16  nop     dword ptr [rax+rax+00h]
0x140040d1b  test    eax, eax
0x140040d1d  jnz     short loc_140040D23
0x140040d1f  bts     ebx, 10h
0x140040d23  inc     rbp
0x140040d26  lea     rdi, [r14+rbp*8]
0x140040d2a  mov     rax, [rdi]
0x140040d2d  test    rax, rax
0x140040d30  jnz     loc_140040BFF
0x140040d36  mov     rbp, [rsp+38h+arg_8]
0x140040d3b  mov     eax, ebx
0x140040d3d  mov     rbx, [rsp+38h+arg_0]
0x140040d42  mov     [r15], esi
0x140040d45  mov     rsi, [rsp+38h+arg_10]
0x140040d4a  add     rsp, 20h
0x140040d4e  pop     r15
0x140040d50  pop     r14
0x140040d52  pop     rdi
0x140040d53  retn
```
