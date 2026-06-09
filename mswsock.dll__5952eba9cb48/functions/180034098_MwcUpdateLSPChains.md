# MwcUpdateLSPChains

- ea: `0x180034098`
- end: `0x180034395`
- name: `MwcUpdateLSPChains`
- size: `765`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800328c0`

## callees

- `0x180022bd2`
- `0x1800327a8`
- `0x180033500`
- `0x180033744`
- `0x180033a4c`
- `0x180034098`
- `0x180038104`
- `0x18003a928`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180034330`
- `ntdll!RtlFreeHeap` at `0x180034373`
- `ntdll!RtlFreeHeap` at `0x180034330`
- `ntdll!RtlFreeHeap` at `0x180034373`

## pseudocode

```c
BOOLEAN __fastcall MwcUpdateLSPChains(char a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5)
{
  unsigned int v5; // esi
  BOOLEAN result; // al
  _DWORD *v9; // rbx
  PVOID v10; // r8
  size_t v11; // rdi
  char *HeapRoutine; // rax
  char *v13; // r14
  unsigned int v14; // ecx
  unsigned int v15; // edx
  __int64 v16; // rax
  __int64 v17; // r13
  unsigned int v18; // edi
  int v19; // r10d
  __int64 v20; // r8
  int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // r8
  unsigned int i; // ecx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  unsigned int j; // edi
  unsigned int v31; // [rsp+30h] [rbp-48h] BYREF
  PVOID P; // [rsp+38h] [rbp-40h] BYREF
  __int64 v33; // [rsp+40h] [rbp-38h]
  unsigned int v36; // [rsp+98h] [rbp+20h] BYREF

  v5 = 0;
  P = 0;
  v36 = 0;
  v31 = 0;
  result = MwcGetProtoArray(a1, (int **)&P, &v36, &v31, a5);
  if ( v36 && v31 )
  {
    v9 = P;
    if ( (unsigned __int8)MwcMapNewCatalogIds(a2, a3, P, v36) )
    {
      v11 = 16LL * v31;
      HeapRoutine = (char *)SockAllocateHeapRoutine(SockPrivateHeap, 0, v11);
      v13 = HeapRoutine;
      if ( HeapRoutine )
      {
        memset_0(HeapRoutine, 0, v11);
        v14 = 0;
        LODWORD(P) = 0;
        if ( a3 )
        {
          v15 = a3;
          v16 = 0;
          v33 = 0;
          do
          {
            v17 = 628 * v16;
            if ( *(_DWORD *)(a2 + 628 * v16 + 40) == 1 && *(_DWORD *)(a2 + v17 + 108) == 2 )
            {
              v18 = 0;
LABEL_16:
              v19 = *(_DWORD *)(a2 + v17 + 36);
              while ( v18 < v36 )
              {
                v20 = 628LL * v18;
                v21 = v9[(unsigned __int64)v20 / 4 + 10];
                if ( (unsigned int)(v21 - 2) <= 5 )
                {
                  v22 = (unsigned int)(v21 - 1);
                  if ( (unsigned int)v22 < 7 )
                  {
                    v23 = v22 + 157LL * v18;
                    if ( v9[v23 + 11] == v19 )
                    {
                      v24 = *(_DWORD *)(a2 + v17 + 112);
                      v9[v23 + 11] = v24;
                      if ( (xmmword_180063D60 & 2) != 0 )
                        WPP_SF_SLL(v23, v18, v20, v20 + (_DWORD)v9 + 116, v19, v24);
                      if ( v18 < v36 )
                      {
                        if ( v31 && v5 < v31 )
                        {
                          v25 = 157LL * v18;
                          for ( i = 0; i < v5; ++i )
                          {
                            v27 = 16LL * i;
                            v28 = *(_QWORD *)&v9[v25 + 5] - *(_QWORD *)&v13[v27];
                            if ( !v28 )
                              v28 = *(_QWORD *)&v9[v25 + 7] - *(_QWORD *)&v13[v27 + 8];
                            if ( !v28 )
                              goto LABEL_34;
                          }
                          v29 = 2LL * v5++;
                          *(_OWORD *)&v13[8 * v29] = *(_OWORD *)&v9[v25 + 5];
                        }
LABEL_34:
                        if ( ++v18 <= v36 )
                          goto LABEL_16;
                      }
                      break;
                    }
                  }
                }
                ++v18;
              }
              v16 = v33;
              v14 = (unsigned int)P;
              v15 = a3;
            }
            ++v14;
            ++v16;
            LODWORD(P) = v14;
            v33 = v16;
          }
          while ( v14 < v15 );
        }
        for ( j = 0; j < v5; ++j )
          MwcUpdateLSP(a1, (__int64)&v13[16 * j], (__int64)v9, v36, a5);
        RtlFreeHeap(SockPrivateHeap, 0, v13);
      }
      else
      {
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_(1025, 68, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids);
        LogError(8, L"Failed to allocate space for LSPs");
      }
    }
    else if ( (xmmword_180063D60 & 2) != 0 )
    {
      WPP_SF_(1025, 67, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids);
    }
    v10 = v9;
    return RtlFreeHeap(SockPrivateHeap, 0, v10);
  }
  if ( (xmmword_180063D60 & 2) != 0 )
    result = WPP_SF_(1025, 66, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids);
  v10 = P;
  if ( P )
    return RtlFreeHeap(SockPrivateHeap, 0, v10);
  return result;
}

```

## disassembly

```asm
0x180034098  mov     r11, rsp
0x18003409b  mov     [r11+10h], rbx
0x18003409f  mov     [r11+20h], r9d
0x1800340a3  mov     [r11+18h], r8d
0x1800340a7  mov     [rsp+arg_0], cl
0x1800340ab  push    rsi
0x1800340ac  push    rdi
0x1800340ad  push    r13
0x1800340af  push    r14
0x1800340b1  push    r15
0x1800340b3  sub     rsp, 50h
0x1800340b7  mov     al, cl
0x1800340b9  lea     r9, [r11-48h]
0x1800340bd  mov     rcx, [rsp+78h+arg_20]
0x1800340c5  xor     esi, esi
0x1800340c7  mov     [r11-58h], rcx
0x1800340cb  mov     r13d, r8d
0x1800340ce  mov     r15, rdx
0x1800340d1  mov     [r11-40h], rsi
0x1800340d5  mov     cl, al
0x1800340d7  mov     [r11+20h], esi
0x1800340db  lea     r8, [r11+20h]
0x1800340df  mov     [rsp+78h+var_48], esi
0x1800340e3  lea     rdx, [r11-40h]
0x1800340e7  call    MwcGetProtoArray
0x1800340ec  cmp     [rsp+78h+arg_18], esi
0x1800340f3  jz      loc_180034341
0x1800340f9  cmp     [rsp+78h+var_48], esi
0x1800340fd  jz      loc_180034341
0x180034103  mov     rbx, [rsp+78h+P]
0x180034108  mov     edx, r13d
0x18003410b  mov     r9d, [rsp+78h+arg_18]
0x180034113  mov     r8, rbx
0x180034116  mov     rcx, r15
0x180034119  call    MwcMapNewCatalogIds
0x18003411e  test    al, al
0x180034120  jnz     short loc_180034147
0x180034122  test    byte ptr cs:xmmword_180063D60, 2
0x180034129  jz      short loc_18003413F
0x18003412b  lea     edx, [rsi+43h]
0x18003412e  mov     ecx, 401h
0x180034133  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x18003413a  call    WPP_SF_
0x18003413f  mov     r8, rbx
0x180034142  jmp     loc_18003436A
0x180034147  mov     edi, [rsp+78h+var_48]
0x18003414b  xor     edx, edx
0x18003414d  mov     rcx, cs:SockPrivateHeap
0x180034154  mov     rax, cs:SockAllocateHeapRoutine
0x18003415b  shl     rdi, 4
0x18003415f  mov     r8, rdi
0x180034162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034167  mov     r14, rax
0x18003416a  test    rax, rax
0x18003416d  jnz     short loc_18003419F
0x18003416f  test    byte ptr cs:xmmword_180063D60, 2
0x180034176  jz      short loc_18003418C
0x180034178  lea     edx, [rax+44h]
0x18003417b  mov     ecx, 401h
0x180034180  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180034187  call    WPP_SF_
0x18003418c  lea     rdx, aFailedToAlloca_4; "Failed to allocate space for LSPs"
0x180034193  mov     ecx, 8
0x180034198  call    LogError
0x18003419d  jmp     short loc_18003413F
0x18003419f  mov     r8, rdi; Size
0x1800341a2  xor     edx, edx; Val
0x1800341a4  mov     rcx, r14; void *
0x1800341a7  call    memset_0
0x1800341ac  xor     ecx, ecx
0x1800341ae  mov     dword ptr [rsp+78h+P], ecx
0x1800341b2  test    r13d, r13d
0x1800341b5  jz      loc_1800342E7
0x1800341bb  mov     edx, [rsp+78h+arg_10]
0x1800341c2  xor     eax, eax
0x1800341c4  mov     [rsp+78h+var_38], rax
0x1800341c9  imul    r13, rax, 274h
0x1800341d0  cmp     dword ptr [r15+r13+28h], 1
0x1800341d6  jnz     loc_1800342D1
0x1800341dc  cmp     dword ptr [r15+r13+6Ch], 2
0x1800341e2  jnz     loc_1800342D1
0x1800341e8  xor     edi, edi
0x1800341ea  mov     r10d, [r15+r13+24h]
0x1800341ef  cmp     edi, [rsp+78h+arg_18]
0x1800341f6  jnb     loc_1800342C1
0x1800341fc  mov     edx, edi
0x1800341fe  imul    r8, rdx, 274h
0x180034205  mov     ecx, [r8+rbx+28h]
0x18003420a  lea     eax, [rcx-2]
0x18003420d  cmp     eax, 5
0x180034210  ja      short loc_18003422B
0x180034212  lea     eax, [rcx-1]
0x180034215  cmp     eax, 7
0x180034218  jnb     short loc_18003422B
0x18003421a  imul    rcx, rdx, 9Dh
0x180034221  add     rcx, rax
0x180034224  cmp     [rbx+rcx*4+2Ch], r10d
0x180034229  jz      short loc_18003422F
0x18003422b  inc     edi
0x18003422d  jmp     short loc_1800341EF
0x18003422f  mov     eax, [r15+r13+70h]
0x180034234  mov     [rbx+rcx*4+2Ch], eax
0x180034238  test    byte ptr cs:xmmword_180063D60, 2
0x18003423f  jz      short loc_180034256
0x180034241  mov     [rsp+78h+var_50], eax
0x180034245  lea     r9, [rbx+74h]
0x180034249  add     r9, r8
0x18003424c  mov     dword ptr [rsp+78h+var_58], r10d
0x180034251  call    WPP_SF_SLL
0x180034256  cmp     edi, [rsp+78h+arg_18]
0x18003425d  jnb     short loc_1800342C1
0x18003425f  cmp     [rsp+78h+var_48], 1
0x180034264  jb      short loc_1800342B2
0x180034266  cmp     esi, [rsp+78h+var_48]
0x18003426a  jnb     short loc_1800342B2
0x18003426c  mov     eax, edi
0x18003426e  imul    r8, rax, 274h
0x180034275  xor     ecx, ecx
0x180034277  cmp     ecx, esi
0x180034279  jnb     short loc_18003429F
0x18003427b  mov     rax, [r8+rbx+14h]
0x180034280  mov     edx, ecx
0x180034282  shl     rdx, 4
0x180034286  sub     rax, [rdx+r14]
0x18003428a  jnz     short loc_180034296
0x18003428c  mov     rax, [r8+rbx+1Ch]
0x180034291  sub     rax, [rdx+r14+8]
0x180034296  test    rax, rax
0x180034299  jz      short loc_1800342B2
0x18003429b  inc     ecx
0x18003429d  jmp     short loc_180034277
0x18003429f  movups  xmm0, xmmword ptr [r8+rbx+14h]
0x1800342a5  mov     eax, esi
0x1800342a7  add     rax, rax
0x1800342aa  inc     esi
0x1800342ac  movdqu  xmmword ptr [r14+rax*8], xmm0
0x1800342b2  inc     edi
0x1800342b4  cmp     edi, [rsp+78h+arg_18]
0x1800342bb  jbe     loc_1800341EA
0x1800342c1  mov     rax, [rsp+78h+var_38]
0x1800342c6  mov     ecx, dword ptr [rsp+78h+P]
0x1800342ca  mov     edx, [rsp+78h+arg_10]
0x1800342d1  inc     ecx
0x1800342d3  inc     rax
0x1800342d6  mov     dword ptr [rsp+78h+P], ecx
0x1800342da  mov     [rsp+78h+var_38], rax
0x1800342df  cmp     ecx, edx
0x1800342e1  jb      loc_1800341C9
0x1800342e7  xor     edi, edi
0x1800342e9  test    esi, esi
0x1800342eb  jz      short loc_180034324
0x1800342ed  mov     r15b, [rsp+78h+arg_0]
0x1800342f5  mov     rax, [rsp+78h+arg_20]
0x1800342fd  mov     r8, rbx
0x180034300  mov     r9d, [rsp+78h+arg_18]
0x180034308  mov     cl, r15b
0x18003430b  mov     edx, edi
0x18003430d  shl     rdx, 4
0x180034311  add     rdx, r14
0x180034314  mov     [rsp+78h+var_58], rax
0x180034319  call    MwcUpdateLSP
0x18003431e  inc     edi
0x180034320  cmp     edi, esi
0x180034322  jb      short loc_1800342F5
0x180034324  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003432b  mov     r8, r14; P
0x18003432e  xor     edx, edx; Flags
0x180034330  call    cs:__imp_RtlFreeHeap
0x180034337  nop     dword ptr [rax+rax+00h]
0x18003433c  jmp     loc_18003413F
0x180034341  test    byte ptr cs:xmmword_180063D60, 2
0x180034348  jz      short loc_180034360
0x18003434a  mov     edx, 42h ; 'B'
0x18003434f  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180034356  mov     ecx, 401h
0x18003435b  call    WPP_SF_
0x180034360  mov     r8, [rsp+78h+P]; P
0x180034365  test    r8, r8
0x180034368  jz      short loc_18003437F
0x18003436a  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180034371  xor     edx, edx; Flags
0x180034373  call    cs:__imp_RtlFreeHeap
0x18003437a  nop     dword ptr [rax+rax+00h]
0x18003437f  mov     rbx, [rsp+78h+arg_8]
0x180034387  add     rsp, 50h
0x18003438b  pop     r15
0x18003438d  pop     r14
0x18003438f  pop     r13
0x180034391  pop     rdi
0x180034392  pop     rsi
0x180034393  retn
```
