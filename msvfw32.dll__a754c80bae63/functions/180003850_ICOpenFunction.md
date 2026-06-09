# ICOpenFunction

- ea: `0x180003850`
- end: `0x180003958`
- name: `ICOpenFunction`
- size: `264`
- prototype: `HIC __stdcall(DWORD fccType, DWORD fccHandler, UINT wMode, FARPROC lpfnHandler)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800074a0`

## callees

- `0x18000250c`
- `0x180002640`
- `0x180003850`
- `0x180003a60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800038e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000393d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800038e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000393d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003894`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003894`
- `api-ms-win-core-stringansi-l1-1-0!CharLowerBuffA` at `0x1800038a3`
- `api-ms-win-core-stringansi-l1-1-0!CharLowerBuffA` at `0x1800038b2`
- `api-ms-win-core-stringansi-l1-1-0!CharLowerBuffA` at `0x1800038a3`
- `api-ms-win-core-stringansi-l1-1-0!CharLowerBuffA` at `0x1800038b2`

## pseudocode

```c
HIC __stdcall ICOpenFunction(DWORD fccType, DWORD fccHandler, UINT wMode, FARPROC lpfnHandler)
{
  HIC result; // rax
  _DWORD *Converter; // rax
  __int64 v8; // rdx
  HIC v9; // rbx
  HIC v10; // rcx
  DWORD v11; // eax
  LONG_PTR v12; // rax
  DWORD_PTR dw2[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v14; // [rsp+30h] [rbp-30h]
  __int128 v15; // [rsp+40h] [rbp-20h]
  __int64 v16; // [rsp+50h] [rbp-10h]
  DWORD sz; // [rsp+70h] [rbp+10h] BYREF
  DWORD v18; // [rsp+78h] [rbp+18h] BYREF

  v18 = fccHandler;
  sz = fccType;
  result = 0;
  v16 = 0;
  *(_OWORD *)dw2 = 0;
  v14 = 0;
  v15 = 0;
  if ( lpfnHandler )
  {
    EnterCriticalSection(&ICOpenCritSec);
    CharLowerBuffA((LPSTR)&sz, 4u);
    CharLowerBuffA((LPSTR)&v18, 4u);
    HIDWORD(dw2[0]) = sz;
    LODWORD(dw2[1]) = v18;
    LODWORD(dw2[0]) = 56;
    LODWORD(v14) = wMode;
    Converter = (_DWORD *)FindConverter(0, 0);
    v9 = (HIC)Converter;
    if ( Converter )
    {
      *Converter = 1734438227;
      Converter[4] = sz;
      v10 = (HIC)Converter;
      v11 = v18;
      *((_QWORD *)v9 + 4) = v8;
      *((_QWORD *)v9 + 3) = v8;
      *((_DWORD *)v9 + 5) = v11;
      *((_QWORD *)v9 + 5) = lpfnHandler;
      v12 = ICSendMessage(v10, 3u, 0, (DWORD_PTR)dw2);
      if ( v12 )
      {
        *((_QWORD *)v9 + 4) = v12;
      }
      else
      {
        ICClose(v9);
        v9 = 0;
      }
      LeaveCriticalSection(&ICOpenCritSec);
      return v9;
    }
    else
    {
      LeaveCriticalSection(&ICOpenCritSec);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003850  mov     rax, rsp
0x180003853  mov     [rax+18h], rbx
0x180003857  mov     [rax+20h], rdi
0x18000385b  mov     [rax+10h], edx
0x18000385e  mov     [rax+8], ecx
0x180003861  push    rbp
0x180003862  mov     rbp, rsp
0x180003865  sub     rsp, 60h
0x180003869  xorps   xmm0, xmm0
0x18000386c  xor     eax, eax
0x18000386e  mov     [rbp+var_10], rax
0x180003872  mov     rdi, r9
0x180003875  mov     ebx, r8d
0x180003878  movups  xmmword ptr [rbp+dw2], xmm0
0x18000387c  movups  [rbp+var_30], xmm0
0x180003880  movups  [rbp+var_20], xmm0
0x180003884  test    r9, r9
0x180003887  jz      loc_180003946
0x18000388d  lea     rcx, ICOpenCritSec; lpCriticalSection
0x180003894  call    cs:__imp_EnterCriticalSection
0x18000389a  mov     edx, 4; cchLength
0x18000389f  lea     rcx, [rbp+sz]; lpsz
0x1800038a3  call    cs:__imp_CharLowerBuffA
0x1800038a9  mov     edx, 4; cchLength
0x1800038ae  lea     rcx, [rbp+arg_8]; lpsz
0x1800038b2  call    cs:__imp_CharLowerBuffA
0x1800038b8  mov     eax, [rbp+sz]
0x1800038bb  xor     edx, edx
0x1800038bd  mov     dword ptr [rbp+dw2+4], eax
0x1800038c0  xor     ecx, ecx
0x1800038c2  mov     eax, [rbp+arg_8]
0x1800038c5  mov     dword ptr [rbp+dw2+8], eax
0x1800038c8  mov     dword ptr [rbp+dw2], 38h ; '8'
0x1800038cf  mov     dword ptr [rbp+var_30], ebx
0x1800038d2  call    FindConverter
0x1800038d7  mov     rbx, rax
0x1800038da  test    rax, rax
0x1800038dd  jnz     short loc_1800038F0
0x1800038df  lea     rcx, ICOpenCritSec; lpCriticalSection
0x1800038e6  call    cs:__imp_LeaveCriticalSection
0x1800038ec  xor     eax, eax
0x1800038ee  jmp     short loc_180003946
0x1800038f0  mov     dword ptr [rax], 67616D53h
0x1800038f6  lea     r9, [rbp+dw2]; dw2
0x1800038fa  mov     eax, [rbp+sz]
0x1800038fd  xor     r8d, r8d; dw1
0x180003900  mov     [rbx+10h], eax
0x180003903  mov     rcx, rbx; hic
0x180003906  mov     eax, [rbp+arg_8]
0x180003909  mov     [rbx+20h], rdx
0x18000390d  mov     [rbx+18h], rdx
0x180003911  lea     edx, [r8+3]; msg
0x180003915  mov     [rbx+14h], eax
0x180003918  mov     [rbx+28h], rdi
0x18000391c  call    ICSendMessage
0x180003921  test    rax, rax
0x180003924  jnz     short loc_180003932
0x180003926  mov     rcx, rbx; hic
0x180003929  call    ICClose
0x18000392e  xor     ebx, ebx
0x180003930  jmp     short loc_180003936
0x180003932  mov     [rbx+20h], rax
0x180003936  lea     rcx, ICOpenCritSec; lpCriticalSection
0x18000393d  call    cs:__imp_LeaveCriticalSection
0x180003943  mov     rax, rbx
0x180003946  lea     r11, [rsp+60h+var_s0]
0x18000394b  mov     rbx, [r11+20h]
0x18000394f  mov     rdi, [r11+28h]
0x180003953  mov     rsp, r11
0x180003956  pop     rbp
0x180003957  retn
```
