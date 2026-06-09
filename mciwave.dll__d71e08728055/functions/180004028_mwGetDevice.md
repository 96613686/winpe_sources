# mwGetDevice

- ea: `0x180004028`
- end: `0x1800040d3`
- name: `mwGetDevice`
- size: `171`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000492c`
- `0x180004d18`

## callees

- `0x180003b30`
- `0x180004028`

## import_xrefs

- `WINMM!waveInOpen` at `0x180004095`
- `WINMM!waveInOpen` at `0x180004095`
- `WINMM!waveOutOpen` at `0x180004060`
- `WINMM!waveOutOpen` at `0x180004060`

## pseudocode

```c
__int64 __fastcall mwGetDevice(__int64 a1)
{
  const WAVEFORMATEX *v1; // r8
  unsigned int v2; // ebx
  DWORD_PTR v4; // r9
  int v5; // edx
  int v6; // edx

  v1 = *(const WAVEFORMATEX **)(a1 + 168);
  v2 = 0;
  v4 = *(unsigned int *)(a1 + 24);
  if ( *(_DWORD *)(a1 + 28) == 1 )
  {
    if ( waveOutOpen((LPHWAVEOUT)(a1 + 48), *(_DWORD *)(a1 + 36), v1, v4, 0, 0x20000u) )
    {
      v5 = *(_DWORD *)(a1 + 28);
      *(_QWORD *)(a1 + 48) = 0;
      v2 = mwCheckDevice(a1, v5);
      if ( !v2 )
        return (unsigned int)(*(_DWORD *)(a1 + 36) != -1) + 320;
    }
  }
  else if ( waveInOpen((LPHWAVEIN)(a1 + 56), *(_DWORD *)(a1 + 40), v1, v4, 0, 0x20000u) )
  {
    v6 = *(_DWORD *)(a1 + 28);
    *(_QWORD *)(a1 + 56) = 0;
    v2 = mwCheckDevice(a1, v6);
    if ( !v2 )
      return (unsigned int)(*(_DWORD *)(a1 + 40) != -1) + 322;
  }
  return v2;
}

```

## disassembly

```asm
0x180004028  mov     rax, rsp
0x18000402b  mov     [rax+8], rbx
0x18000402f  mov     [rax+10h], rsi
0x180004033  push    rdi
0x180004034  sub     rsp, 30h
0x180004038  mov     r8, [rcx+0A8h]; pwfx
0x18000403f  xor     ebx, ebx
0x180004041  cmp     dword ptr [rcx+1Ch], 1
0x180004045  mov     rdi, rcx
0x180004048  mov     r9d, [rcx+18h]; dwCallback
0x18000404c  mov     dword ptr [rax-10h], 20000h
0x180004053  mov     [rax-18h], rbx
0x180004057  jnz     short loc_18000408E
0x180004059  mov     edx, [rcx+24h]; uDeviceID
0x18000405c  add     rcx, 30h ; '0'; phwo
0x180004060  call    cs:__imp_waveOutOpen
0x180004066  test    eax, eax
0x180004068  jz      short loc_1800040C1
0x18000406a  mov     edx, [rdi+1Ch]
0x18000406d  mov     rcx, rdi
0x180004070  mov     [rdi+30h], rbx
0x180004074  call    mwCheckDevice
0x180004079  mov     ebx, eax
0x18000407b  test    eax, eax
0x18000407d  jnz     short loc_1800040C1
0x18000407f  cmp     dword ptr [rdi+24h], 0FFFFFFFFh
0x180004083  setnz   bl
0x180004086  add     ebx, 140h
0x18000408c  jmp     short loc_1800040C1
0x18000408e  mov     edx, [rcx+28h]; uDeviceID
0x180004091  add     rcx, 38h ; '8'; phwi
0x180004095  call    cs:__imp_waveInOpen
0x18000409b  test    eax, eax
0x18000409d  jz      short loc_1800040C1
0x18000409f  mov     edx, [rdi+1Ch]
0x1800040a2  mov     rcx, rdi
0x1800040a5  mov     [rdi+38h], rbx
0x1800040a9  call    mwCheckDevice
0x1800040ae  mov     ebx, eax
0x1800040b0  test    eax, eax
0x1800040b2  jnz     short loc_1800040C1
0x1800040b4  cmp     dword ptr [rdi+28h], 0FFFFFFFFh
0x1800040b8  setnz   bl
0x1800040bb  add     ebx, 142h
0x1800040c1  mov     rsi, [rsp+38h+arg_8]
0x1800040c6  mov     eax, ebx
0x1800040c8  mov     rbx, [rsp+38h+arg_0]
0x1800040cd  add     rsp, 30h
0x1800040d1  pop     rdi
0x1800040d2  retn
```
