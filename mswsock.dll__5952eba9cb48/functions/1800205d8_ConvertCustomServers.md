# ConvertCustomServers

- ea: `0x1800205d8`
- end: `0x1800207c0`
- name: `ConvertCustomServers`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180016120`

## callees

- `0x1800205d8`
- `0x180029a14`
- `0x18002a98c`
- `0x18002a9f0`

## import_xrefs

- `DNSAPI!DnsApiAllocZero` at `0x180020651`
- `DNSAPI!DnsApiAllocZero` at `0x180020651`
- `DNSAPI!DnsStringCopyAllocateEx` at `0x1800206ef`
- `DNSAPI!DnsStringCopyAllocateEx` at `0x1800206ef`
- `DNSAPI!DnsFreeCustomServers` at `0x18002079a`
- `DNSAPI!DnsFreeCustomServers` at `0x18002079a`

## pseudocode

```c
__int64 __fastcall ConvertCustomServers(unsigned int a1, __int64 a2, unsigned int *a3, __int64 *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // r15
  rsize_t v11; // rdx
  __int64 v12; // rbx
  int v13; // eax
  void *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned int v18; // [rsp+50h] [rbp+30h] BYREF
  __int64 v19; // [rsp+60h] [rbp+40h] BYREF

  v18 = a1;
  v19 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 && (*a4 = 0, a3) && (a1 == 0) == (a2 == 0) )
  {
    v7 = 0;
    if ( a1 )
    {
      v19 = DnsApiAllocZero(56 * a1);
      v8 = v19;
      if ( v19 )
      {
        v9 = v18;
        v10 = 0;
        if ( v18 )
        {
          while ( 1 )
          {
            v11 = (unsigned int)(*(_DWORD *)(a2 + 40 * v10) - 1);
            if ( *(_DWORD *)(a2 + 40 * v10) == 1 )
            {
              v12 = 56LL * (unsigned int)v10;
              *(_DWORD *)(v12 + v8) = 1;
            }
            else
            {
              v11 = (unsigned int)(*(_DWORD *)(a2 + 40 * v10) - 2);
              if ( *(_DWORD *)(a2 + 40 * v10) == 2 )
              {
                v12 = 56LL * (unsigned int)v10;
                *(_DWORD *)(v12 + v8) = 2;
              }
              else
              {
                if ( *(_DWORD *)(a2 + 40 * v10) != 3 )
                  goto LABEL_31;
                v12 = 56LL * (unsigned int)v10;
                *(_DWORD *)(v12 + v8) = 3;
              }
              if ( *(_QWORD *)(a2 + 40 * v10 + 32) )
              {
                v13 = (Feature_5977_1413__private_featureState & 0x10) != 0
                    ? Feature_5977_1413__private_featureState & 1
                    : Feature_5977_1413__private_IsEnabledDeviceUsageNoInline(v8, v11, (unsigned int)v10);
                v14 = *(void **)(a2 + 40 * v10 + 32);
                v15 = v13 ? SaBlob_StringCopyAllocW(v14) : DnsStringCopyAllocateEx(v14, 0, 1);
                *(_QWORD *)(v12 + v19 + 16) = v15;
                if ( !*(_QWORD *)(v12 + v19 + 16) )
                  goto LABEL_8;
              }
            }
            v16 = *(_QWORD *)(a2 + 40 * v10 + 8);
            if ( v16 )
            {
              if ( v16 != 1 )
                goto LABEL_31;
              *(_QWORD *)(v12 + v19 + 8) |= 1uLL;
            }
            v7 = memcpy_s(
                   (void *const)(v12 + v19 + 24),
                   v11,
                   *(const void *const *)(a2 + 40 * v10 + 24),
                   *(unsigned int *)(a2 + 40 * v10 + 16));
            if ( v7 )
              break;
            v9 = v18;
            v10 = (unsigned int)(v10 + 1);
            v8 = v19;
            if ( (unsigned int)v10 >= v18 )
              goto LABEL_30;
          }
        }
        else
        {
LABEL_30:
          *a4 = v8;
          *a3 = v9;
          v19 = 0;
          v18 = 0;
        }
      }
      else
      {
LABEL_8:
        v7 = 8;
      }
    }
  }
  else
  {
LABEL_31:
    v7 = 87;
  }
  DnsFreeCustomServers(&v18, &v19);
  return v7;
}

```

## disassembly

```asm
0x1800205d8  mov     [rsp-28h+arg_8], rbx
0x1800205dd  mov     [rsp-28h+arg_18], rsi
0x1800205e2  mov     [rsp-28h+arg_0], ecx
0x1800205e6  push    rbp
0x1800205e7  push    rdi
0x1800205e8  push    r12
0x1800205ea  push    r14
0x1800205ec  push    r15
0x1800205ee  mov     rbp, rsp
0x1800205f1  sub     rsp, 20h
0x1800205f5  mov     [rbp+arg_10], 0
0x1800205fd  mov     rdi, rdx
0x180020600  mov     edx, ecx
0x180020602  mov     r12, r9
0x180020605  mov     r14, r8
0x180020608  test    r8, r8
0x18002060b  jz      short loc_180020614
0x18002060d  mov     dword ptr [r8], 0
0x180020614  test    r12, r12
0x180020617  jz      loc_18002078D
0x18002061d  mov     qword ptr [r9], 0
0x180020624  test    r14, r14
0x180020627  jz      loc_18002078D
0x18002062d  xor     ecx, ecx
0x18002062f  test    edx, edx
0x180020631  setz    cl
0x180020634  xor     eax, eax
0x180020636  test    rdi, rdi
0x180020639  setz    al
0x18002063c  cmp     ecx, eax
0x18002063e  jnz     loc_18002078D
0x180020644  xor     ebx, ebx
0x180020646  test    edx, edx
0x180020648  jz      loc_180020792
0x18002064e  imul    ecx, edx, 38h ; '8'
0x180020651  call    cs:__imp_DnsApiAllocZero
0x180020658  nop     dword ptr [rax+rax+00h]
0x18002065d  mov     [rbp+arg_10], rax
0x180020661  mov     rcx, rax
0x180020664  test    rax, rax
0x180020667  jnz     short loc_180020673
0x180020669  mov     ebx, 8
0x18002066e  jmp     loc_180020792
0x180020673  mov     eax, [rbp+arg_0]
0x180020676  xor     r15d, r15d
0x180020679  test    eax, eax
0x18002067b  jz      loc_180020775
0x180020681  lea     rsi, [r15+r15*4]
0x180020685  mov     r8d, r15d
0x180020688  mov     edx, [rdi+rsi*8]
0x18002068b  sub     edx, 1; DestinationSize
0x18002068e  jz      loc_180020719
0x180020694  sub     edx, 1
0x180020697  jz      short loc_1800206AF
0x180020699  cmp     edx, 1
0x18002069c  jnz     loc_18002078D
0x1800206a2  imul    rbx, r8, 38h ; '8'
0x1800206a6  mov     dword ptr [rbx+rcx], 3
0x1800206ad  jmp     short loc_1800206BA
0x1800206af  imul    rbx, r8, 38h ; '8'
0x1800206b3  mov     dword ptr [rbx+rcx], 2
0x1800206ba  cmp     qword ptr [rdi+rsi*8+20h], 0
0x1800206c0  jz      short loc_180020724
0x1800206c2  mov     eax, cs:Feature_5977_1413__private_featureState
0x1800206c8  test    al, 10h
0x1800206ca  jz      short loc_1800206D1
0x1800206cc  and     eax, 1
0x1800206cf  jmp     short loc_1800206D6
0x1800206d1  call    Feature_5977_1413__private_IsEnabledDeviceUsageNoInline
0x1800206d6  mov     rcx, [rdi+rsi*8+20h]; Src
0x1800206db  test    eax, eax
0x1800206dd  jz      short loc_1800206E6
0x1800206df  call    SaBlob_StringCopyAllocW
0x1800206e4  jmp     short loc_1800206FB
0x1800206e6  xor     edx, edx
0x1800206e8  lea     r9d, [rdx+1]
0x1800206ec  mov     r8d, r9d
0x1800206ef  call    cs:__imp_DnsStringCopyAllocateEx
0x1800206f6  nop     dword ptr [rax+rax+00h]
0x1800206fb  mov     rcx, rax
0x1800206fe  mov     rax, [rbp+arg_10]
0x180020702  mov     [rbx+rax+10h], rcx
0x180020707  mov     rax, [rbp+arg_10]
0x18002070b  cmp     qword ptr [rbx+rax+10h], 0
0x180020711  jz      loc_180020669
0x180020717  jmp     short loc_180020724
0x180020719  imul    rbx, r8, 38h ; '8'
0x18002071d  mov     dword ptr [rbx+rcx], 1
0x180020724  mov     rax, [rdi+rsi*8+8]
0x180020729  test    rax, rax
0x18002072c  jz      short loc_180020742
0x18002072e  cmp     rax, 1
0x180020732  jnz     short loc_18002078D
0x180020734  test    al, al
0x180020736  jz      short loc_180020742
0x180020738  mov     rax, [rbp+arg_10]
0x18002073c  or      qword ptr [rbx+rax+8], 1
0x180020742  mov     rcx, [rbp+arg_10]
0x180020746  mov     r9d, [rdi+rsi*8+10h]; SourceSize
0x18002074b  add     rcx, 18h
0x18002074f  mov     r8, [rdi+rsi*8+18h]; Source
0x180020754  add     rcx, rbx; Destination
0x180020757  call    memcpy_s
0x18002075c  mov     ebx, eax
0x18002075e  test    eax, eax
0x180020760  jnz     short loc_180020792
0x180020762  mov     eax, [rbp+arg_0]
0x180020765  inc     r15d
0x180020768  mov     rcx, [rbp+arg_10]
0x18002076c  cmp     r15d, eax
0x18002076f  jb      loc_180020681
0x180020775  mov     [r12], rcx
0x180020779  mov     [r14], eax
0x18002077c  mov     [rbp+arg_10], 0
0x180020784  mov     [rbp+arg_0], 0
0x18002078b  jmp     short loc_180020792
0x18002078d  mov     ebx, 57h ; 'W'
0x180020792  lea     rdx, [rbp+arg_10]
0x180020796  lea     rcx, [rbp+arg_0]
0x18002079a  call    cs:__imp_DnsFreeCustomServers
0x1800207a1  nop     dword ptr [rax+rax+00h]
0x1800207a6  mov     rsi, [rsp+20h+arg_18]
0x1800207ab  mov     eax, ebx
0x1800207ad  mov     rbx, [rsp+20h+arg_8]
0x1800207b2  add     rsp, 20h
0x1800207b6  pop     r15
0x1800207b8  pop     r14
0x1800207ba  pop     r12
0x1800207bc  pop     rdi
0x1800207bd  pop     rbp
0x1800207be  retn
```
