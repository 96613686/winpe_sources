# CDigitalAudio::PRELToPFRACT(long)

- ea: `0x18000d0f0`
- end: `0x18000d215`
- name: `?PRELToPFRACT@CDigitalAudio@@SAJJ@Z`
- size: `293`
- prototype: `__int64 __fastcall(int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bb20`
- `0x18000d3b0`
- `0x18000dca0`
- `0x18000ddf0`

## callees

- `0x18000d0f0`

## pseudocode

```c
__int64 __fastcall CDigitalAudio::PRELToPFRACT(int a1)
{
  unsigned int v1; // r8d
  int v3; // r8d

  if ( a1 <= 100 )
  {
    if ( a1 >= -100 )
    {
      return (unsigned int)dword_18001FDB0[a1];
    }
    else
    {
      v3 = -4800;
      if ( a1 >= -4800 )
        v3 = a1;
      return (unsigned int)((*((_DWORD *)&CDigitalAudio::m_spfSemiTones + 48 - v3 / -100 % 12)
                           * (*((int *)&CDigitalAudio::m_spfCents + 100 - -v3 % 100) >> ((char)v3 / 80))) >> 12);
    }
  }
  else
  {
    v1 = 4800;
    if ( a1 <= 4800 )
      v1 = a1;
    return (unsigned int)((*((_DWORD *)&CDigitalAudio::m_spfSemiTones
                           + (int)(v1 / 0x64 + 12 * (4 - (int)(v1 / 0x64) / 12)))
                         * (*((_DWORD *)&CDigitalAudio::m_spfCents + (int)(v1 % 0x64 + 100)) << ((int)(v1 / 0x64) / 12))) >> 12);
  }
}

```

## disassembly

```asm
0x18000d0f0  lea     r10, cs:180000000h
0x18000d0f7  cmp     ecx, 64h ; 'd'
0x18000d0fa  jle     short loc_18000D160
0x18000d0fc  mov     r8d, 12C0h
0x18000d102  mov     eax, 51EB851Fh
0x18000d107  cmp     ecx, r8d
0x18000d10a  cmovle  r8d, ecx
0x18000d10e  mul     r8d
0x18000d111  mov     eax, 2AAAAAABh
0x18000d116  mov     r9d, edx
0x18000d119  shr     r9d, 5
0x18000d11d  imul    r9d
0x18000d120  sar     edx, 1
0x18000d122  mov     eax, edx
0x18000d124  shr     eax, 1Fh
0x18000d127  add     edx, eax
0x18000d129  imul    eax, r9d, 64h ; 'd'
0x18000d12d  mov     ecx, edx
0x18000d12f  sub     r8d, eax
0x18000d132  lea     eax, [r8+64h]
0x18000d136  cdqe
0x18000d138  mov     eax, rva ?m_spfCents@CDigitalAudio@@0PAJA[r10+rax*4]; long near * CDigitalAudio::m_spfCents ...
0x18000d140  shl     eax, cl
0x18000d142  mov     ecx, 4
0x18000d147  sub     ecx, edx
0x18000d149  lea     ecx, [rcx+rcx*2]
0x18000d14c  lea     edx, [r9+rcx*4]
0x18000d150  movsxd  rcx, edx
0x18000d153  imul    eax, rva ?m_spfSemiTones@CDigitalAudio@@0PAJA[r10+rcx*4]; long near * CDigitalAudio::m_spfSemiTones ...
0x18000d15c  sar     eax, 0Ch
0x18000d15f  retn
0x18000d160  cmp     ecx, 0FFFFFF9Ch
0x18000d163  jge     loc_18000D209
0x18000d169  mov     r8d, 0FFFFED40h
0x18000d16f  mov     eax, 51EB851Fh
0x18000d174  cmp     ecx, r8d
0x18000d177  cmovge  r8d, ecx
0x18000d17b  mov     ecx, r8d
0x18000d17e  neg     ecx
0x18000d180  imul    ecx
0x18000d182  sar     edx, 5
0x18000d185  mov     eax, edx
0x18000d187  shr     eax, 1Fh
0x18000d18a  add     edx, eax
0x18000d18c  imul    eax, edx, 64h ; 'd'
0x18000d18f  sub     ecx, eax
0x18000d191  mov     eax, 64h ; 'd'
0x18000d196  sub     eax, ecx
0x18000d198  movsxd  rcx, eax
0x18000d19b  mov     eax, 0E4B17E4Bh
0x18000d1a0  imul    r8d
0x18000d1a3  mov     r9d, rva ?m_spfCents@CDigitalAudio@@0PAJA[r10+rcx*4]; long near * CDigitalAudio::m_spfCents ...
0x18000d1ab  sar     edx, 7
0x18000d1ae  mov     eax, edx
0x18000d1b0  shr     eax, 1Fh
0x18000d1b3  add     edx, eax
0x18000d1b5  mov     eax, 0AE147AE1h
0x18000d1ba  movzx   ecx, dl
0x18000d1bd  imul    r8d
0x18000d1c0  sar     r9d, cl
0x18000d1c3  mov     r8d, edx
0x18000d1c6  sar     r8d, 5
0x18000d1ca  mov     eax, r8d
0x18000d1cd  shr     eax, 1Fh
0x18000d1d0  add     r8d, eax
0x18000d1d3  mov     eax, 2AAAAAABh
0x18000d1d8  imul    r8d
0x18000d1db  sar     edx, 1
0x18000d1dd  mov     eax, edx
0x18000d1df  shr     eax, 1Fh
0x18000d1e2  add     edx, eax
0x18000d1e4  lea     ecx, [rdx+rdx*2]
0x18000d1e7  shl     ecx, 2
0x18000d1ea  sub     r8d, ecx
0x18000d1ed  mov     ecx, 30h ; '0'
0x18000d1f2  sub     ecx, r8d
0x18000d1f5  movsxd  rdx, ecx
0x18000d1f8  imul    r9d, rva ?m_spfSemiTones@CDigitalAudio@@0PAJA[r10+rdx*4]; long near * CDigitalAudio::m_spfSemiTones ...
0x18000d201  sar     r9d, 0Ch
0x18000d205  mov     eax, r9d
0x18000d208  retn
0x18000d209  movsxd  rax, ecx
0x18000d20c  mov     eax, rva dword_18001FDB0[r10+rax*4]
0x18000d214  retn
```
