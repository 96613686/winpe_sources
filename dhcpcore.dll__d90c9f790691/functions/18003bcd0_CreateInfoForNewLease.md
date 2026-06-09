# CreateInfoForNewLease

- ea: `0x18003bcd0`
- end: `0x18003beb4`
- name: `CreateInfoForNewLease`
- size: `484`
- prototype: `__int64 __fastcall(u_long *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003c064`

## callees

- `0x18003bcd0`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003bda4`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003bde0`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003be1c`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003be52`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003bda4`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003bde0`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003be1c`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003be52`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18003bd0f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18003bd0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003bdad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003bde9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003be25`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003be5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003bdad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003bde9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003be25`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003be5b`
- `WS2_32!__imp_ntohl` at `0x18003bd28`
- `WS2_32!__imp_ntohl` at `0x18003bd37`
- `WS2_32!__imp_ntohl` at `0x18003bd43`
- `WS2_32!__imp_ntohl` at `0x18003bd28`
- `WS2_32!__imp_ntohl` at `0x18003bd37`
- `WS2_32!__imp_ntohl` at `0x18003bd43`

## pseudocode

```c
__int64 __fastcall CreateInfoForNewLease(u_long *a1, _QWORD *a2)
{
  unsigned int v4; // ebp
  _DWORD *v5; // rbx
  int v6; // r14d
  int v7; // edi
  int v8; // esi
  int v9; // esi
  int v10; // r14d
  int v11; // esi
  int v12; // esi
  int v13; // r14d
  int v14; // esi
  int v15; // esi
  int v16; // esi
  int v17; // edi

  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 18, WPP_c84194e7b785338e3b207dae288fd792_Traceguids);
  v4 = 0;
  *a2 = 0;
  v5 = LocalAlloc(0x40u, 0x30u);
  if ( v5 )
  {
    v5[4] = ntohl(a1[30]);
    v5[6] = ntohl(a1[32]);
    v5[5] = ntohl(a1[31]);
    v5[7] = a1[110];
    v5[8] = a1[112];
    v5[9] = a1[114];
    v5[10] = a1[116];
    v5[11] = a1[118];
    if ( a1[199] != 1 )
    {
      v6 = v5[8];
      v7 = -1;
      if ( v6 == -1 )
      {
        v8 = -1;
      }
      else
      {
        v9 = _time64(0);
        v8 = v6 + v9 - GetTickCount64() / 0x3E8;
      }
      v10 = v5[9];
      v5[8] = v8;
      if ( v10 == -1 )
      {
        v11 = -1;
      }
      else
      {
        v12 = _time64(0);
        v11 = v10 + v12 - GetTickCount64() / 0x3E8;
      }
      v13 = v5[10];
      v5[9] = v11;
      if ( v13 == -1 )
      {
        v14 = -1;
      }
      else
      {
        v15 = _time64(0);
        v14 = v13 + v15 - GetTickCount64() / 0x3E8;
      }
      v5[10] = v14;
      v16 = v5[11];
      if ( v16 != -1 )
      {
        v17 = _time64(0);
        v7 = v16 + v17 - GetTickCount64() / 0x3E8;
      }
      v5[11] = v7;
    }
    *a2 = v5;
  }
  else
  {
    v4 = 8;
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 19, WPP_c84194e7b785338e3b207dae288fd792_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18003bcd0  push    rbx
0x18003bcd2  push    rbp
0x18003bcd3  push    rsi
0x18003bcd4  push    rdi
0x18003bcd5  push    r13
0x18003bcd7  push    r14
0x18003bcd9  push    r15
0x18003bcdb  sub     rsp, 20h
0x18003bcdf  mov     r15, rdx
0x18003bce2  mov     rdi, rcx
0x18003bce5  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003bcec  jz      short loc_18003BD04
0x18003bcee  mov     edx, 12h
0x18003bcf3  lea     r8, WPP_c84194e7b785338e3b207dae288fd792_Traceguids
0x18003bcfa  mov     ecx, 404h
0x18003bcff  call    WPP_SF_
0x18003bd04  xor     ebp, ebp
0x18003bd06  mov     [r15], rbp
0x18003bd09  lea     edx, [rbp+30h]; uBytes
0x18003bd0c  lea     ecx, [rbp+40h]; uFlags
0x18003bd0f  call    cs:__imp_LocalAlloc
0x18003bd15  mov     rbx, rax
0x18003bd18  test    rax, rax
0x18003bd1b  jnz     short loc_18003BD25
0x18003bd1d  lea     ebp, [rax+8]
0x18003bd20  jmp     loc_18003BE81
0x18003bd25  mov     ecx, [rdi+78h]; netlong
0x18003bd28  call    cs:__imp_ntohl
0x18003bd2e  mov     [rbx+10h], eax
0x18003bd31  mov     ecx, [rdi+80h]; netlong
0x18003bd37  call    cs:__imp_ntohl
0x18003bd3d  mov     [rbx+18h], eax
0x18003bd40  mov     ecx, [rdi+7Ch]; netlong
0x18003bd43  call    cs:__imp_ntohl
0x18003bd49  mov     [rbx+14h], eax
0x18003bd4c  mov     eax, [rdi+1B8h]
0x18003bd52  mov     [rbx+1Ch], eax
0x18003bd55  mov     eax, [rdi+1C0h]
0x18003bd5b  mov     [rbx+20h], eax
0x18003bd5e  mov     eax, [rdi+1C8h]
0x18003bd64  mov     [rbx+24h], eax
0x18003bd67  mov     eax, [rdi+1D0h]
0x18003bd6d  mov     [rbx+28h], eax
0x18003bd70  mov     eax, [rdi+1D8h]
0x18003bd76  mov     [rbx+2Ch], eax
0x18003bd79  mov     eax, [rdi+31Ch]
0x18003bd7f  cmp     eax, 1
0x18003bd82  jz      loc_18003BE7E
0x18003bd88  mov     r14d, [rbx+20h]
0x18003bd8c  or      edi, 0FFFFFFFFh
0x18003bd8f  mov     r13, 624DD2F1A9FBE77h
0x18003bd99  cmp     r14d, edi
0x18003bd9c  jnz     short loc_18003BDA2
0x18003bd9e  mov     esi, edi
0x18003bda0  jmp     short loc_18003BDCE
0x18003bda2  xor     ecx, ecx; Time
0x18003bda4  call    cs:__imp__time64
0x18003bdaa  mov     rsi, rax
0x18003bdad  call    cs:__imp_GetTickCount64
0x18003bdb3  mov     rcx, rax
0x18003bdb6  mov     rax, r13
0x18003bdb9  mul     rcx
0x18003bdbc  sub     rcx, rdx
0x18003bdbf  shr     rcx, 1
0x18003bdc2  add     rcx, rdx
0x18003bdc5  shr     rcx, 9
0x18003bdc9  sub     esi, ecx
0x18003bdcb  add     esi, r14d
0x18003bdce  mov     r14d, [rbx+24h]
0x18003bdd2  mov     [rbx+20h], esi
0x18003bdd5  cmp     r14d, edi
0x18003bdd8  jnz     short loc_18003BDDE
0x18003bdda  mov     esi, edi
0x18003bddc  jmp     short loc_18003BE0A
0x18003bdde  xor     ecx, ecx; Time
0x18003bde0  call    cs:__imp__time64
0x18003bde6  mov     rsi, rax
0x18003bde9  call    cs:__imp_GetTickCount64
0x18003bdef  mov     rcx, rax
0x18003bdf2  mov     rax, r13
0x18003bdf5  mul     rcx
0x18003bdf8  sub     rcx, rdx
0x18003bdfb  shr     rcx, 1
0x18003bdfe  add     rcx, rdx
0x18003be01  shr     rcx, 9
0x18003be05  sub     esi, ecx
0x18003be07  add     esi, r14d
0x18003be0a  mov     r14d, [rbx+28h]
0x18003be0e  mov     [rbx+24h], esi
0x18003be11  cmp     r14d, edi
0x18003be14  jnz     short loc_18003BE1A
0x18003be16  mov     esi, edi
0x18003be18  jmp     short loc_18003BE46
0x18003be1a  xor     ecx, ecx; Time
0x18003be1c  call    cs:__imp__time64
0x18003be22  mov     rsi, rax
0x18003be25  call    cs:__imp_GetTickCount64
0x18003be2b  mov     rcx, rax
0x18003be2e  mov     rax, r13
0x18003be31  mul     rcx
0x18003be34  sub     rcx, rdx
0x18003be37  shr     rcx, 1
0x18003be3a  add     rcx, rdx
0x18003be3d  shr     rcx, 9
0x18003be41  sub     esi, ecx
0x18003be43  add     esi, r14d
0x18003be46  mov     [rbx+28h], esi
0x18003be49  mov     esi, [rbx+2Ch]
0x18003be4c  cmp     esi, edi
0x18003be4e  jz      short loc_18003BE7B
0x18003be50  xor     ecx, ecx; Time
0x18003be52  call    cs:__imp__time64
0x18003be58  mov     rdi, rax
0x18003be5b  call    cs:__imp_GetTickCount64
0x18003be61  mov     rcx, rax
0x18003be64  mov     rax, r13
0x18003be67  mul     rcx
0x18003be6a  sub     rcx, rdx
0x18003be6d  shr     rcx, 1
0x18003be70  add     rcx, rdx
0x18003be73  shr     rcx, 9
0x18003be77  sub     edi, ecx
0x18003be79  add     edi, esi
0x18003be7b  mov     [rbx+2Ch], edi
0x18003be7e  mov     [r15], rbx
0x18003be81  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003be88  jz      short loc_18003BEA3
0x18003be8a  mov     edx, 13h
0x18003be8f  lea     r8, WPP_c84194e7b785338e3b207dae288fd792_Traceguids
0x18003be96  mov     ecx, 404h
0x18003be9b  mov     r9d, ebp
0x18003be9e  call    WPP_SF_D
0x18003bea3  mov     eax, ebp
0x18003bea5  add     rsp, 20h
0x18003bea9  pop     r15
0x18003beab  pop     r14
0x18003bead  pop     r13
0x18003beaf  pop     rdi
0x18003beb0  pop     rsi
0x18003beb1  pop     rbp
0x18003beb2  pop     rbx
0x18003beb3  retn
```
