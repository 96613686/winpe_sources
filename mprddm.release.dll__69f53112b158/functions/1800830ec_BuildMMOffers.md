# BuildMMOffers

- ea: `0x1800830ec`
- end: `0x18008339b`
- name: `BuildMMOffers`
- size: `687`
- prototype: `__int64 __fastcall(int, int, int, int, int, BYTE Data, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180083654`
- `0x180083de8`

## callees

- `0x1800830ec`
- `0x180085cb4`
- `0x18008769c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180083224`
- `ADVAPI32!RegOpenKeyExW` at `0x180083224`
- `ADVAPI32!RegQueryValueExW` at `0x18008325f`
- `ADVAPI32!RegQueryValueExW` at `0x18008325f`
- `ADVAPI32!RegCloseKey` at `0x180083283`
- `ADVAPI32!RegCloseKey` at `0x180083283`

## string_xrefs

- `0x180083212`: `System\CurrentControlSet\Services\Rasman\Parameters`

## pseudocode

```c
void __fastcall BuildMMOffers(__int64 a1, _DWORD *a2, _DWORD *a3, int a4, int a5, int Data, __int64 a7)
{
  int DH2048_AES256RegValue; // r14d
  int v11; // esi
  int *v12; // rdx
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // edx
  __int64 v16; // rsi
  __int64 v17; // rbx
  int v18; // ecx
  bool v19; // zf
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+50h] BYREF

  *a2 = 0;
  *a3 = 0;
  if ( !a4 )
    goto LABEL_7;
  DH2048_AES256RegValue = ReadDH2048_AES256RegValue();
  v11 = 28800;
  if ( a7 )
  {
    v11 = *(_DWORD *)(a7 + 24);
    v12 = *(int **)(a7 + 16);
    if ( v12 )
    {
      v13 = *v12;
      v14 = v12[1];
      v15 = v12[5];
      *(_QWORD *)(a1 + 4) = 0;
      *(_DWORD *)a1 = v14;
      *(_DWORD *)(a1 + 12) = v13;
      *(_DWORD *)(a1 + 16) = v11;
      *(_QWORD *)(a1 + 20) = v15;
LABEL_20:
      ++*a2;
      return;
    }
  }
  if ( !DH2048_AES256RegValue )
    goto LABEL_7;
  RasIpsecTrace("NegotiateDH2048_AES256= %d");
  *(_QWORD *)(a1 + 4) = 0;
  *(_DWORD *)a1 = 4;
  *(_DWORD *)(a1 + 12) = 1;
  *(_DWORD *)(a1 + 16) = v11;
  *(_QWORD *)(a1 + 20) = 3;
  a1 += 28;
  ++*a2;
  if ( DH2048_AES256RegValue != 2 )
  {
LABEL_7:
    *(_QWORD *)(a1 + 4) = 0;
    v16 = a1;
    *(_DWORD *)a1 = 4;
    *(_DWORD *)(a1 + 12) = 1;
    *(_DWORD *)(a1 + 16) = 28800;
    *(_QWORD *)(a1 + 20) = 5;
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 40) = 0;
    *(_DWORD *)(a1 + 28) = 2;
    *(_DWORD *)(a1 + 40) = 1;
    *(_DWORD *)(a1 + 44) = 28800;
    *(_QWORD *)(a1 + 48) = 4;
    v17 = a1 + 56;
    *a2 += 2;
    if ( !a4 )
    {
      *(_QWORD *)(v16 + 60) = 0;
      v17 += 56;
      *(_QWORD *)(v16 + 68) = 0;
      *(_DWORD *)(v16 + 56) = 4;
      *(_DWORD *)(v16 + 68) = 1;
      *(_DWORD *)(v16 + 72) = 28800;
      *(_QWORD *)(v16 + 76) = 3;
      ++*a2;
      *(_QWORD *)(v16 + 88) = 0;
      *(_QWORD *)(v16 + 96) = 0;
      *(_DWORD *)(v16 + 84) = 1;
      *(_DWORD *)(v16 + 96) = 1;
      *(_DWORD *)(v16 + 100) = 28800;
      *(_QWORD *)(v16 + 104) = 3;
      ++*a2;
LABEL_18:
      *(_QWORD *)(v17 + 4) = 0;
      v19 = g_dwAllowL2TPWeakCrypto == 0;
      *(_DWORD *)v17 = 1;
      *(_DWORD *)(v17 + 12) = 1;
      *(_DWORD *)(v17 + 16) = 28800;
      *(_QWORD *)(v17 + 20) = 2;
      if ( !v19 )
      {
        *(_QWORD *)(v17 + 32) = 0;
        *(_QWORD *)(v17 + 40) = 0;
        *(_DWORD *)(v17 + 28) = 1;
        *(_DWORD *)(v17 + 40) = 0;
        *(_DWORD *)(v17 + 44) = 28800;
        *(_QWORD *)(v17 + 48) = 2;
        *(_QWORD *)(v17 + 60) = 0;
        *(_QWORD *)(v17 + 68) = 0;
        *(_DWORD *)(v17 + 56) = 0;
        *(_DWORD *)(v17 + 68) = 1;
        *(_DWORD *)(v17 + 72) = 28800;
        *(_QWORD *)(v17 + 76) = 1;
        *(_QWORD *)(v17 + 88) = 0;
        *(_QWORD *)(v17 + 96) = 0;
        *(_DWORD *)(v17 + 84) = 0;
        *(_DWORD *)(v17 + 96) = 0;
        *(_DWORD *)(v17 + 100) = 28800;
        *(_QWORD *)(v17 + 104) = 1;
        *a2 += 3;
      }
      goto LABEL_20;
    }
    hKey = 0;
    Type = 0;
    Data = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Rasman\\Parameters", 0, 1u, &hKey) )
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"NegotiateDH2048", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 || cbData != 4 )
        Data = 0;
      RegCloseKey(hKey);
    }
    v18 = Data;
    if ( (unsigned int)(Data - 1) > 1 )
      goto LABEL_18;
    *(_QWORD *)(v16 + 60) = 0;
    *(_QWORD *)(v16 + 68) = 0;
    *(_QWORD *)(v16 + 76) = 0;
    *(_DWORD *)v17 = 1;
    *(_DWORD *)(v17 + 12) = 1;
    *(_DWORD *)(v17 + 16) = 28800;
    *(_QWORD *)(v17 + 20) = 3;
    v17 += 28;
    ++*a2;
    if ( v18 != 2 )
      goto LABEL_18;
  }
}

```

## disassembly

```asm
0x1800830ec  mov     [rsp-38h+arg_18], rbx
0x1800830f1  push    rbp
0x1800830f2  push    rsi
0x1800830f3  push    rdi
0x1800830f4  push    r12
0x1800830f6  push    r13
0x1800830f8  push    r14
0x1800830fa  push    r15
0x1800830fc  mov     rbp, rsp
0x1800830ff  sub     rsp, 30h
0x180083103  xor     r12d, r12d
0x180083106  mov     r15d, r9d
0x180083109  mov     [rdx], r12d
0x18008310c  mov     rdi, rdx
0x18008310f  mov     [r8], r12d
0x180083112  mov     rbx, rcx
0x180083115  mov     r14d, 7080h
0x18008311b  lea     r13d, [r12+1]
0x180083120  test    r9d, r9d
0x180083123  jz      loc_1800831AF
0x180083129  call    ReadDH2048_AES256RegValue
0x18008312e  mov     rdx, [rbp+arg_30]
0x180083132  mov     r14d, eax
0x180083135  mov     esi, 7080h
0x18008313a  test    rdx, rdx
0x18008313d  jz      short loc_18008316B
0x18008313f  mov     esi, [rdx+18h]
0x180083142  mov     rdx, [rdx+10h]
0x180083146  test    rdx, rdx
0x180083149  jz      short loc_18008316B
0x18008314b  mov     ecx, [rdx]
0x18008314d  mov     eax, [rdx+4]
0x180083150  mov     edx, [rdx+14h]
0x180083153  mov     [rbx+4], r12
0x180083157  mov     [rbx], eax
0x180083159  mov     [rbx+0Ch], ecx
0x18008315c  mov     [rbx+10h], esi
0x18008315f  mov     [rbx+14h], edx
0x180083162  mov     [rbx+18h], r12d
0x180083166  jmp     loc_18008337F
0x18008316b  test    r14d, r14d
0x18008316e  jz      short loc_1800831A9
0x180083170  mov     edx, r14d
0x180083173  lea     rcx, aNegotiatedh204_0; "NegotiateDH2048_AES256= %d"
0x18008317a  call    RasIpsecTrace
0x18008317f  mov     [rbx+4], r12
0x180083183  mov     dword ptr [rbx], 4
0x180083189  mov     [rbx+0Ch], r13d
0x18008318d  mov     [rbx+10h], esi
0x180083190  mov     qword ptr [rbx+14h], 3
0x180083198  add     rbx, 1Ch
0x18008319c  add     [rdi], r13d
0x18008319f  cmp     r14d, 2
0x1800831a3  jz      loc_180083382
0x1800831a9  mov     r14d, 7080h
0x1800831af  mov     [rbx+4], r12
0x1800831b3  mov     rsi, rbx
0x1800831b6  mov     dword ptr [rbx], 4
0x1800831bc  mov     [rbx+0Ch], r13d
0x1800831c0  mov     [rbx+10h], r14d
0x1800831c4  mov     qword ptr [rbx+14h], 5
0x1800831cc  mov     [rbx+20h], r12
0x1800831d0  mov     [rbx+28h], r12
0x1800831d4  mov     dword ptr [rbx+1Ch], 2
0x1800831db  mov     [rbx+28h], r13d
0x1800831df  mov     [rbx+2Ch], r14d
0x1800831e3  mov     qword ptr [rbx+30h], 4
0x1800831eb  add     rbx, 38h ; '8'
0x1800831ef  add     dword ptr [rdi], 2
0x1800831f2  test    r15d, r15d
0x1800831f5  jz      loc_1800832CB
0x1800831fb  lea     rax, [rbp+hKey]
0x1800831ff  mov     [rbp+hKey], r12
0x180083203  mov     r9d, r13d; samDesired
0x180083206  mov     [rsp+30h+phkResult], rax; phkResult
0x18008320b  xor     r8d, r8d; ulOptions
0x18008320e  mov     [rbp+Type], r12d
0x180083212  lea     rdx, aSystemCurrentc_34; "System\\CurrentControlSet\\Services\\Ra"...
0x180083219  mov     dword ptr [rbp+Data], r12d
0x18008321d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180083224  call    cs:__imp_RegOpenKeyExW
0x18008322b  nop     dword ptr [rax+rax+00h]
0x180083230  test    eax, eax
0x180083232  jnz     short loc_18008328F
0x180083234  mov     rcx, [rbp+hKey]; hKey
0x180083238  lea     rax, [rbp+cbData]
0x18008323c  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180083241  lea     r9, [rbp+Type]; lpType
0x180083245  lea     rax, [rbp+Data]
0x180083249  mov     [rbp+cbData], 4
0x180083250  xor     r8d, r8d; lpReserved
0x180083253  mov     [rsp+30h+phkResult], rax; lpData
0x180083258  lea     rdx, aNegotiatedh204_1; "NegotiateDH2048"
0x18008325f  call    cs:__imp_RegQueryValueExW
0x180083266  nop     dword ptr [rax+rax+00h]
0x18008326b  test    eax, eax
0x18008326d  jnz     short loc_18008327B
0x18008326f  cmp     [rbp+Type], 4
0x180083273  jnz     short loc_18008327B
0x180083275  cmp     [rbp+cbData], 4
0x180083279  jz      short loc_18008327F
0x18008327b  mov     dword ptr [rbp+Data], r12d
0x18008327f  mov     rcx, [rbp+hKey]; hKey
0x180083283  call    cs:__imp_RegCloseKey
0x18008328a  nop     dword ptr [rax+rax+00h]
0x18008328f  mov     ecx, dword ptr [rbp+Data]
0x180083292  lea     eax, [rcx-1]
0x180083295  cmp     eax, r13d
0x180083298  ja      short loc_180083310
0x18008329a  mov     [rsi+3Ch], r12
0x18008329e  mov     [rsi+44h], r12
0x1800832a2  mov     [rsi+4Ch], r12
0x1800832a6  mov     [rbx], r13d
0x1800832a9  mov     [rbx+0Ch], r13d
0x1800832ad  mov     [rbx+10h], r14d
0x1800832b1  mov     qword ptr [rbx+14h], 3
0x1800832b9  add     rbx, 1Ch
0x1800832bd  add     [rdi], r13d
0x1800832c0  cmp     ecx, 2
0x1800832c3  jz      loc_180083382
0x1800832c9  jmp     short loc_180083310
0x1800832cb  mov     [rsi+3Ch], r12
0x1800832cf  add     rbx, 38h ; '8'
0x1800832d3  mov     [rsi+44h], r12
0x1800832d7  mov     dword ptr [rsi+38h], 4
0x1800832de  mov     [rsi+44h], r13d
0x1800832e2  mov     [rsi+48h], r14d
0x1800832e6  mov     qword ptr [rsi+4Ch], 3
0x1800832ee  add     [rdi], r13d
0x1800832f1  mov     [rsi+58h], r12
0x1800832f5  mov     [rsi+60h], r12
0x1800832f9  mov     [rsi+54h], r13d
0x1800832fd  mov     [rsi+60h], r13d
0x180083301  mov     [rsi+64h], r14d
0x180083305  mov     qword ptr [rsi+68h], 3
0x18008330d  add     [rdi], r13d
0x180083310  mov     [rbx+4], r12
0x180083314  cmp     cs:g_dwAllowL2TPWeakCrypto, r12d
0x18008331b  mov     [rbx], r13d
0x18008331e  mov     [rbx+0Ch], r13d
0x180083322  mov     [rbx+10h], r14d
0x180083326  mov     qword ptr [rbx+14h], 2
0x18008332e  jz      short loc_18008337F
0x180083330  mov     [rbx+20h], r12
0x180083334  mov     [rbx+28h], r12
0x180083338  mov     [rbx+1Ch], r13d
0x18008333c  mov     [rbx+28h], r12d
0x180083340  mov     [rbx+2Ch], r14d
0x180083344  mov     qword ptr [rbx+30h], 2
0x18008334c  mov     [rbx+3Ch], r12
0x180083350  mov     [rbx+44h], r12
0x180083354  mov     [rbx+38h], r12d
0x180083358  mov     [rbx+44h], r13d
0x18008335c  mov     [rbx+48h], r14d
0x180083360  mov     [rbx+4Ch], r13
0x180083364  mov     [rbx+58h], r12
0x180083368  mov     [rbx+60h], r12
0x18008336c  mov     [rbx+54h], r12d
0x180083370  mov     [rbx+60h], r12d
0x180083374  mov     [rbx+64h], r14d
0x180083378  mov     [rbx+68h], r13
0x18008337c  add     dword ptr [rdi], 3
0x18008337f  add     [rdi], r13d
0x180083382  mov     rbx, [rsp+30h+arg_18]
0x18008338a  add     rsp, 30h
0x18008338e  pop     r15
0x180083390  pop     r14
0x180083392  pop     r13
0x180083394  pop     r12
0x180083396  pop     rdi
0x180083397  pop     rsi
0x180083398  pop     rbp
0x180083399  retn
```
