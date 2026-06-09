# GetRealDll(HINSTANCE__ * *,int)

- ea: `0x18002a230`
- end: `0x18002a2dc`
- name: `?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z`
- size: `172`
- prototype: `__int64 __fastcall(HINSTANCE *, int)`
- caller_count: `37`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1800229f0`
- `0x180022be0`
- `0x180022d10`
- `0x180022e20`
- `0x180022f60`
- `0x180023070`
- `0x180023190`
- `0x180023550`
- `0x180023670`
- `0x180023790`
- `0x1800238b0`
- `0x1800243c0`
- `0x1800244e0`
- `0x180024820`
- `0x180025590`
- `0x180025f40`
- `0x1800266f0`
- `0x180026830`
- `0x180026a90`
- `0x180026bc0`
- `0x180026cf0`
- `0x1800288e0`
- `0x180028fe8`
- `0x180029090`
- `0x18002a120`
- `0x18002c160`
- `0x18002cd4c`
- `0x18002d134`
- `0x18002d2a8`
- `0x18002d34c`
- `0x18002d444`
- `0x18002dd2c`
- `0x18002ddc8`
- `0x18002de54`
- `0x18002e490`
- `0x18002e5cc`
- `0x18002e784`

## callees

- `0x180008710`
- `0x180029b70`
- `0x18002a230`
- `0x18002ba30`

## pseudocode

```c
__int64 __fastcall GetRealDll(HINSTANCE *a1, int a2)
{
  int Installation; // ebx
  _OWORD v6[3]; // [rsp+20h] [rbp-59h] BYREF
  __int128 v7; // [rsp+50h] [rbp-29h]
  __int64 v8; // [rsp+60h] [rbp-19h]
  int v9; // [rsp+68h] [rbp-11h]
  __int64 v10; // [rsp+70h] [rbp-9h]
  int v11; // [rsp+78h] [rbp-1h]
  __int64 v12; // [rsp+80h] [rbp+7h]
  __int64 v13; // [rsp+88h] [rbp+Fh]
  __int64 v14; // [rsp+90h] [rbp+17h]
  int v15; // [rsp+98h] [rbp+1Fh]
  __int64 v16; // [rsp+A0h] [rbp+27h]

  memset(v6, 0, sizeof(v6));
  v7 = 0;
  v8 = 1;
  v9 = 0;
  v10 = 0;
  v11 = 1;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = -1;
  DWORD2(v7) = 1;
  Installation = RuntimeRequest::RequestRuntimeDll((RuntimeRequest *)v6, a2, 0);
  if ( Installation >= 0 )
    Installation = GetInstallation(a2, a1, 0);
  RuntimeRequest::~RuntimeRequest((RuntimeRequest *)v6);
  return (unsigned int)Installation;
}

```

## disassembly

```asm
0x18002a230  push    rbp
0x18002a232  push    rbx
0x18002a233  push    rsi
0x18002a234  push    rdi
0x18002a235  lea     rbp, [rsp-3Fh]
0x18002a23a  sub     rsp, 0B8h
0x18002a241  mov     edi, edx
0x18002a243  mov     rsi, rcx
0x18002a246  xorps   xmm0, xmm0
0x18002a249  movdqa  [rbp+57h+var_B0], xmm0
0x18002a24e  xorps   xmm1, xmm1
0x18002a251  movdqa  [rbp+57h+var_A0], xmm1
0x18002a256  movdqa  [rbp+57h+var_90], xmm0
0x18002a25b  movups  [rbp+57h+var_80], xmm1
0x18002a25f  mov     eax, 1
0x18002a264  mov     [rbp+57h+var_70], rax
0x18002a268  mov     [rbp+57h+var_68], 0
0x18002a26f  mov     [rbp+57h+var_60], 0
0x18002a277  mov     [rbp+57h+var_58], eax
0x18002a27a  mov     [rbp+57h+var_50], 0
0x18002a282  mov     [rbp+57h+var_48], 0
0x18002a28a  mov     [rbp+57h+var_40], 0
0x18002a292  mov     [rbp+57h+var_38], 0
0x18002a299  mov     [rbp+57h+var_30], 0FFFFFFFFFFFFFFFFh
0x18002a2a1  mov     dword ptr [rbp+57h+var_80+8], eax
0x18002a2a4  xor     r8d, r8d; int *
0x18002a2a7  lea     rcx, [rbp+57h+var_B0]; this
0x18002a2ab  call    ?RequestRuntimeDll@RuntimeRequest@@QEAAJHPEAH@Z; RuntimeRequest::RequestRuntimeDll(int,int *)
0x18002a2b0  mov     ebx, eax
0x18002a2b2  test    eax, eax
0x18002a2b4  js      short loc_18002A2C5
0x18002a2b6  xor     r8d, r8d; int
0x18002a2b9  mov     rdx, rsi; HINSTANCE *
0x18002a2bc  mov     ecx, edi; int
0x18002a2be  call    ?GetInstallation@@YAJHPEAPEAUHINSTANCE__@@H@Z; GetInstallation(int,HINSTANCE__ * *,int)
0x18002a2c3  mov     ebx, eax
0x18002a2c5  lea     rcx, [rbp+57h+var_B0]; this
0x18002a2c9  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x18002a2ce  mov     eax, ebx
0x18002a2d0  add     rsp, 0B8h
0x18002a2d7  pop     rdi
0x18002a2d8  pop     rsi
0x18002a2d9  pop     rbx
0x18002a2da  pop     rbp
0x18002a2db  retn
```
