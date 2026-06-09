# CalculateSleepDurationForIpv6OnlyConfig

- ea: `0x180020734`
- end: `0x1800207e3`
- name: `CalculateSleepDurationForIpv6OnlyConfig`
- size: `175`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001ef2c`
- `0x180021c14`
- `0x18002f094`

## callees

- `0x180020734`
- `0x180049c24`
- `0x180049c98`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180020743`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180020743`

## pseudocode

```c
__int64 __fastcall CalculateSleepDurationForIpv6OnlyConfig(__int64 a1)
{
  unsigned int v2; // edi
  ULONGLONG TickCount64; // rax
  unsigned __int64 v4; // r9
  ULONGLONG v5; // r8
  unsigned __int128 v6; // rax
  ULONGLONG v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx

  v2 = 0;
  TickCount64 = GetTickCount64();
  v4 = *(_QWORD *)(a1 + 2160);
  v5 = TickCount64;
  v6 = TickCount64 * (unsigned __int128)0x624DD2F1A9FBE77uLL;
  v7 = (*((_QWORD *)&v6 + 1) + ((v5 - *((_QWORD *)&v6 + 1)) >> 1)) >> 9;
  if ( v4 > v7 )
  {
    if ( v4 - v7 <= 0xFFFFFFFF )
    {
      v2 = v4 - v7;
      if ( (xmmword_1800616A0 & 0x10) != 0 )
      {
        v8 = 27;
        v9 = 1028;
        goto LABEL_9;
      }
    }
    else if ( (xmmword_1800616A0 & 2) != 0 )
    {
      WPP_SF_IIId(0xFFFFFFFFLL, *((_QWORD *)&v6 + 1));
    }
  }
  else if ( (xmmword_1800616A0 & 2) != 0 )
  {
    v8 = 25;
    v9 = 1025;
LABEL_9:
    WPP_SF_IId(v9, v8);
  }
  return v2;
}

```

## disassembly

```asm
0x180020734  mov     [rsp+arg_0], rbx
0x180020739  push    rdi
0x18002073a  sub     rsp, 40h
0x18002073e  mov     rbx, rcx
0x180020741  xor     edi, edi
0x180020743  call    cs:__imp_GetTickCount64
0x180020749  mov     r9, [rbx+870h]
0x180020750  mov     r8, rax
0x180020753  mov     rax, 624DD2F1A9FBE77h
0x18002075d  mul     r8
0x180020760  sub     r8, rdx
0x180020763  shr     r8, 1
0x180020766  add     r8, rdx
0x180020769  shr     r8, 9
0x18002076d  cmp     r9, r8
0x180020770  ja      short loc_180020789
0x180020772  test    byte ptr cs:xmmword_1800616A0, 2
0x180020779  jz      short loc_1800207D6
0x18002077b  lea     edx, [rdi+19h]
0x18002077e  mov     dword ptr [rsp+48h+var_20], edi
0x180020782  mov     ecx, 401h
0x180020787  jmp     short loc_1800207CC
0x180020789  mov     rax, r9
0x18002078c  mov     ecx, 0FFFFFFFFh
0x180020791  sub     rax, r8
0x180020794  cmp     rax, rcx
0x180020797  jbe     short loc_1800207B3
0x180020799  test    byte ptr cs:xmmword_1800616A0, 2
0x1800207a0  jz      short loc_1800207D6
0x1800207a2  mov     [rsp+48h+var_20], rax
0x1800207a7  mov     [rsp+48h+var_28], r8
0x1800207ac  call    WPP_SF_IIId
0x1800207b1  jmp     short loc_1800207D6
0x1800207b3  mov     edi, eax
0x1800207b5  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800207bc  jz      short loc_1800207D6
0x1800207be  mov     edx, 1Bh
0x1800207c3  mov     dword ptr [rsp+48h+var_20], eax
0x1800207c7  mov     ecx, 404h
0x1800207cc  mov     [rsp+48h+var_28], r8
0x1800207d1  call    WPP_SF_IId
0x1800207d6  mov     rbx, [rsp+48h+arg_0]
0x1800207db  mov     eax, edi
0x1800207dd  add     rsp, 40h
0x1800207e1  pop     rdi
0x1800207e2  retn
```
