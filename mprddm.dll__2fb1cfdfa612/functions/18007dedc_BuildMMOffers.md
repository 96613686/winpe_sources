# BuildMMOffers

- ea: `0x18007dedc`
- end: `0x18007e15b`
- name: `BuildMMOffers`
- size: `639`
- prototype: `__int64 __fastcall(int, int, int, int, int, DWORD cbData, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18007e3e0`
- `0x18007eb50`

## callees

- `0x18007dedc`
- `0x1800803a8`
- `0x180081b84`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18007e014`
- `ADVAPI32!RegOpenKeyExW` at `0x18007e014`
- `ADVAPI32!RegQueryValueExW` at `0x18007e049`
- `ADVAPI32!RegQueryValueExW` at `0x18007e049`
- `ADVAPI32!RegCloseKey` at `0x18007e067`
- `ADVAPI32!RegCloseKey` at `0x18007e067`

## string_xrefs

- `0x18007dffb`: `System\CurrentControlSet\Services\Rasman\Parameters`

## pseudocode

```c
void __fastcall BuildMMOffers(__int64 a1, _DWORD *a2, _DWORD *a3, int a4, int a5, DWORD cbData, __int64 a7)
{
  int DH2048_AES256RegValue; // r14d
  int v11; // ebx
  int *v12; // rdx
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // edx
  __int64 v16; // rbx
  int v17; // ecx
  bool v18; // zf
  int Data; // [rsp+70h] [rbp+40h] BYREF
  DWORD Type; // [rsp+78h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+50h] BYREF

  *a2 = 0;
  *a3 = 0;
  if ( a4 )
  {
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
LABEL_21:
        ++*a2;
        return;
      }
    }
    if ( DH2048_AES256RegValue )
    {
      RasIpsecTrace("NegotiateDH2048_AES256= %d");
      *(_QWORD *)(a1 + 4) = 0;
      *(_DWORD *)a1 = 4;
      *(_DWORD *)(a1 + 12) = 1;
      *(_DWORD *)(a1 + 16) = v11;
      *(_QWORD *)(a1 + 20) = 3;
      ++*a2;
      if ( DH2048_AES256RegValue == 2 )
        return;
      a1 += 28;
    }
  }
  *(_QWORD *)(a1 + 4) = 0;
  v16 = a1 + 56;
  *(_DWORD *)a1 = 4;
  *(_DWORD *)(a1 + 12) = 1;
  *(_DWORD *)(a1 + 16) = 28800;
  *(_QWORD *)(a1 + 20) = 5;
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 28) = 2;
  *(_DWORD *)(a1 + 40) = 1;
  *(_DWORD *)(a1 + 44) = 28800;
  *(_QWORD *)(a1 + 48) = 4;
  *a2 += 2;
  if ( !a4 )
  {
    *(_QWORD *)(a1 + 60) = 0;
    *(_DWORD *)v16 = 4;
    *(_DWORD *)(a1 + 68) = 1;
    *(_DWORD *)(a1 + 72) = 28800;
    *(_QWORD *)(a1 + 76) = 3;
    ++*a2;
    *(_QWORD *)(a1 + 88) = 0;
    *(_DWORD *)(a1 + 84) = 1;
    *(_DWORD *)(a1 + 96) = 1;
    *(_DWORD *)(a1 + 100) = 28800;
    *(_QWORD *)(a1 + 104) = 3;
    v16 = a1 + 112;
    ++*a2;
LABEL_19:
    *(_QWORD *)(v16 + 4) = 0;
    v18 = g_dwAllowL2TPWeakCrypto == 0;
    *(_DWORD *)v16 = 1;
    *(_DWORD *)(v16 + 12) = 1;
    *(_DWORD *)(v16 + 16) = 28800;
    *(_QWORD *)(v16 + 20) = 2;
    if ( !v18 )
    {
      *(_QWORD *)(v16 + 32) = 0;
      *(_DWORD *)(v16 + 28) = 1;
      *(_DWORD *)(v16 + 40) = 0;
      *(_DWORD *)(v16 + 44) = 28800;
      *(_QWORD *)(v16 + 48) = 2;
      *(_QWORD *)(v16 + 60) = 0;
      *(_DWORD *)(v16 + 56) = 0;
      *(_DWORD *)(v16 + 68) = 1;
      *(_DWORD *)(v16 + 72) = 28800;
      *(_QWORD *)(v16 + 76) = 1;
      *(_QWORD *)(v16 + 88) = 0;
      *(_DWORD *)(v16 + 84) = 0;
      *(_DWORD *)(v16 + 96) = 0;
      *(_DWORD *)(v16 + 100) = 28800;
      *(_QWORD *)(v16 + 104) = 1;
      *a2 += 3;
    }
    goto LABEL_21;
  }
  hKey = 0;
  Type = 0;
  cbData = 4;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Rasman\\Parameters", 0, 1u, &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"NegotiateDH2048", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 || cbData != 4 )
      Data = 0;
    RegCloseKey(hKey);
  }
  v17 = Data;
  if ( (unsigned int)(Data - 1) > 1 )
    goto LABEL_19;
  *(_QWORD *)(a1 + 60) = 0;
  *(_DWORD *)v16 = 1;
  *(_DWORD *)(a1 + 68) = 1;
  *(_DWORD *)(a1 + 72) = 28800;
  *(_QWORD *)(a1 + 76) = 3;
  v16 = a1 + 84;
  ++*a2;
  if ( v17 != 2 )
    goto LABEL_19;
}

```

## disassembly

```asm
0x18007dedc  mov     [rsp-38h+arg_18], rbx
0x18007dee1  push    rbp
0x18007dee2  push    rsi
0x18007dee3  push    rdi
0x18007dee4  push    r12
0x18007dee6  push    r13
0x18007dee8  push    r14
0x18007deea  push    r15
0x18007deec  mov     rbp, rsp
0x18007deef  sub     rsp, 30h
0x18007def3  xor     r12d, r12d
0x18007def6  mov     r15d, r9d
0x18007def9  mov     [rdx], r12d
0x18007defc  mov     rsi, rdx
0x18007deff  mov     [r8], r12d
0x18007df02  mov     rdi, rcx
0x18007df05  mov     r14d, 7080h
0x18007df0b  lea     r13d, [r12+1]
0x18007df10  test    r9d, r9d
0x18007df13  jz      loc_18007DF9F
0x18007df19  call    ReadDH2048_AES256RegValue
0x18007df1e  mov     rdx, [rbp+arg_30]
0x18007df22  mov     r14d, eax
0x18007df25  mov     ebx, 7080h
0x18007df2a  test    rdx, rdx
0x18007df2d  jz      short loc_18007DF5B
0x18007df2f  mov     ebx, [rdx+18h]
0x18007df32  mov     rdx, [rdx+10h]
0x18007df36  test    rdx, rdx
0x18007df39  jz      short loc_18007DF5B
0x18007df3b  mov     ecx, [rdx]
0x18007df3d  mov     eax, [rdx+4]
0x18007df40  mov     edx, [rdx+14h]
0x18007df43  mov     [rdi+4], r12
0x18007df47  mov     [rdi], eax
0x18007df49  mov     [rdi+0Ch], ecx
0x18007df4c  mov     [rdi+10h], ebx
0x18007df4f  mov     [rdi+14h], edx
0x18007df52  mov     [rdi+18h], r12d
0x18007df56  jmp     loc_18007E140
0x18007df5b  test    r14d, r14d
0x18007df5e  jz      short loc_18007DF99
0x18007df60  mov     edx, r14d
0x18007df63  lea     rcx, aNegotiatedh204_0; "NegotiateDH2048_AES256= %d"
0x18007df6a  call    RasIpsecTrace
0x18007df6f  mov     [rdi+4], r12
0x18007df73  mov     dword ptr [rdi], 4
0x18007df79  mov     [rdi+0Ch], r13d
0x18007df7d  mov     [rdi+10h], ebx
0x18007df80  mov     qword ptr [rdi+14h], 3
0x18007df88  add     [rsi], r13d
0x18007df8b  cmp     r14d, 2
0x18007df8f  jz      loc_18007E143
0x18007df95  add     rdi, 1Ch
0x18007df99  mov     r14d, 7080h
0x18007df9f  mov     [rdi+4], r12
0x18007dfa3  lea     rbx, [rdi+38h]
0x18007dfa7  mov     dword ptr [rdi], 4
0x18007dfad  mov     [rdi+0Ch], r13d
0x18007dfb1  mov     [rdi+10h], r14d
0x18007dfb5  mov     qword ptr [rdi+14h], 5
0x18007dfbd  mov     [rdi+20h], r12
0x18007dfc1  mov     dword ptr [rdi+1Ch], 2
0x18007dfc8  mov     [rdi+28h], r13d
0x18007dfcc  mov     [rdi+2Ch], r14d
0x18007dfd0  mov     qword ptr [rdi+30h], 4
0x18007dfd8  add     dword ptr [rsi], 2
0x18007dfdb  test    r15d, r15d
0x18007dfde  jz      loc_18007E0A1
0x18007dfe4  lea     rax, [rbp+hKey]
0x18007dfe8  mov     [rbp+hKey], r12
0x18007dfec  mov     r9d, r13d; samDesired
0x18007dfef  mov     [rsp+30h+phkResult], rax; phkResult
0x18007dff4  xor     r8d, r8d; ulOptions
0x18007dff7  mov     [rbp+Type], r12d
0x18007dffb  lea     rdx, aSystemCurrentc_34; "System\\CurrentControlSet\\Services\\Ra"...
0x18007e002  mov     [rbp+cbData], 4
0x18007e009  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007e010  mov     [rbp+Data], r12d
0x18007e014  call    cs:__imp_RegOpenKeyExW
0x18007e01a  test    eax, eax
0x18007e01c  jnz     short loc_18007E06D
0x18007e01e  mov     rcx, [rbp+hKey]; hKey
0x18007e022  lea     rax, [rbp+cbData]
0x18007e026  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18007e02b  lea     r9, [rbp+Type]; lpType
0x18007e02f  lea     rax, [rbp+Data]
0x18007e033  mov     [rbp+cbData], 4
0x18007e03a  xor     r8d, r8d; lpReserved
0x18007e03d  mov     [rsp+30h+phkResult], rax; lpData
0x18007e042  lea     rdx, aNegotiatedh204_1; "NegotiateDH2048"
0x18007e049  call    cs:__imp_RegQueryValueExW
0x18007e04f  test    eax, eax
0x18007e051  jnz     short loc_18007E05F
0x18007e053  cmp     [rbp+Type], 4
0x18007e057  jnz     short loc_18007E05F
0x18007e059  cmp     [rbp+cbData], 4
0x18007e05d  jz      short loc_18007E063
0x18007e05f  mov     [rbp+Data], r12d
0x18007e063  mov     rcx, [rbp+hKey]; hKey
0x18007e067  call    cs:__imp_RegCloseKey
0x18007e06d  mov     ecx, [rbp+Data]
0x18007e070  lea     eax, [rcx-1]
0x18007e073  cmp     eax, r13d
0x18007e076  ja      short loc_18007E0DD
0x18007e078  mov     [rdi+3Ch], r12
0x18007e07c  mov     [rbx], r13d
0x18007e07f  mov     [rbx+0Ch], r13d
0x18007e083  mov     [rbx+10h], r14d
0x18007e087  mov     qword ptr [rbx+14h], 3
0x18007e08f  add     rbx, 1Ch
0x18007e093  add     [rsi], r13d
0x18007e096  cmp     ecx, 2
0x18007e099  jz      loc_18007E143
0x18007e09f  jmp     short loc_18007E0DD
0x18007e0a1  mov     [rdi+3Ch], r12
0x18007e0a5  mov     dword ptr [rbx], 4
0x18007e0ab  mov     [rbx+0Ch], r13d
0x18007e0af  mov     [rbx+10h], r14d
0x18007e0b3  mov     qword ptr [rbx+14h], 3
0x18007e0bb  add     [rsi], r13d
0x18007e0be  mov     [rdi+58h], r12
0x18007e0c2  mov     [rbx+1Ch], r13d
0x18007e0c6  mov     [rbx+28h], r13d
0x18007e0ca  mov     [rbx+2Ch], r14d
0x18007e0ce  mov     qword ptr [rbx+30h], 3
0x18007e0d6  add     rbx, 38h ; '8'
0x18007e0da  add     [rsi], r13d
0x18007e0dd  mov     [rbx+4], r12
0x18007e0e1  cmp     cs:g_dwAllowL2TPWeakCrypto, r12d
0x18007e0e8  mov     [rbx], r13d
0x18007e0eb  mov     [rbx+0Ch], r13d
0x18007e0ef  mov     [rbx+10h], r14d
0x18007e0f3  mov     qword ptr [rbx+14h], 2
0x18007e0fb  jz      short loc_18007E140
0x18007e0fd  mov     [rbx+20h], r12
0x18007e101  mov     [rbx+1Ch], r13d
0x18007e105  mov     [rbx+28h], r12d
0x18007e109  mov     [rbx+2Ch], r14d
0x18007e10d  mov     qword ptr [rbx+30h], 2
0x18007e115  mov     [rbx+3Ch], r12
0x18007e119  mov     [rbx+38h], r12d
0x18007e11d  mov     [rbx+44h], r13d
0x18007e121  mov     [rbx+48h], r14d
0x18007e125  mov     [rbx+4Ch], r13
0x18007e129  mov     [rbx+58h], r12
0x18007e12d  mov     [rbx+54h], r12d
0x18007e131  mov     [rbx+60h], r12d
0x18007e135  mov     [rbx+64h], r14d
0x18007e139  mov     [rbx+68h], r13
0x18007e13d  add     dword ptr [rsi], 3
0x18007e140  add     [rsi], r13d
0x18007e143  mov     rbx, [rsp+30h+arg_18]
0x18007e14b  add     rsp, 30h
0x18007e14f  pop     r15
0x18007e151  pop     r14
0x18007e153  pop     r13
0x18007e155  pop     r12
0x18007e157  pop     rdi
0x18007e158  pop     rsi
0x18007e159  pop     rbp
0x18007e15a  retn
```
