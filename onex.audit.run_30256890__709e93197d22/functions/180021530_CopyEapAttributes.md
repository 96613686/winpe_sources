# CopyEapAttributes

- ea: `0x180021530`
- end: `0x1800217c0`
- name: `CopyEapAttributes`
- size: `656`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001ec18`
- `0x18002b6d0`

## callees

- `0x180005440`
- `0x180010ae0`
- `0x1800214f0`
- `0x180021530`
- `0x180022000`
- `0x18002f705`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x1800215b1`
- `MobileNetworking!AllocateMemory` at `0x180021657`
- `MobileNetworking!AllocateMemory` at `0x1800216eb`
- `MobileNetworking!AllocateMemory` at `0x1800215b1`
- `MobileNetworking!AllocateMemory` at `0x180021657`
- `MobileNetworking!AllocateMemory` at `0x1800216eb`

## string_xrefs

- `0x1800215a0`: `CopyEapAttributes`
- `0x180021641`: `CopyEapAttributes`
- `0x1800216d3`: `CopyEapAttributes`

## pseudocode

```c
__int64 __fastcall CopyEapAttributes(_QWORD *a1, unsigned int *a2)
{
  _QWORD *v4; // rcx
  unsigned int v5; // ebp
  unsigned int Memory; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  unsigned int i; // r14d
  __int64 v12; // rsi
  __int64 v13; // rcx
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v15 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 50, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *a2;
  if ( *a2 )
  {
    if ( *((_QWORD *)a2 + 1) )
      goto LABEL_6;
LABEL_12:
    v7 = 87;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 1) != 0 )
    {
      v10 = 51;
LABEL_31:
      WPP_SF_(v4[7], v10, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids);
    }
    goto LABEL_32;
  }
  if ( *((_QWORD *)a2 + 1) )
    goto LABEL_12;
LABEL_6:
  Memory = AllocateMemory(16, &v15, "CopyEapAttributes", 938);
  v7 = Memory;
  if ( !Memory )
  {
    *(_DWORD *)v15 = *a2;
    *(_QWORD *)(v15 + 8) = 0;
    if ( *((_QWORD *)a2 + 1) )
    {
      Memory = AllocateMemory(16 * v5, v15 + 8, "CopyEapAttributes", 946);
      v7 = Memory;
      if ( Memory )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_32;
        v9 = 53;
        goto LABEL_10;
      }
      for ( i = 0; i < v5; ++i )
      {
        v12 = 16LL * i;
        *(_DWORD *)(*(_QWORD *)(v15 + 8) + v12 + 4) = *(_DWORD *)(v12 + *((_QWORD *)a2 + 1) + 4);
        *(_DWORD *)(v12 + *(_QWORD *)(v15 + 8)) = *(_DWORD *)(v12 + *((_QWORD *)a2 + 1));
        v13 = *(unsigned int *)(v12 + *((_QWORD *)a2 + 1) + 4);
        if ( !(_DWORD)v13 )
        {
          v7 = 87;
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            v10 = 54;
            goto LABEL_31;
          }
          goto LABEL_32;
        }
        Memory = AllocateMemory(v13, v12 + *(_QWORD *)(v15 + 8) + 8LL, "CopyEapAttributes", 961);
        v7 = Memory;
        if ( Memory )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            v9 = 55;
            goto LABEL_10;
          }
          goto LABEL_32;
        }
        memcpy_0(
          *(void **)(*(_QWORD *)(v15 + 8) + v12 + 8),
          *(const void **)(v12 + *((_QWORD *)a2 + 1) + 8),
          *(unsigned int *)(*(_QWORD *)(v15 + 8) + v12 + 4));
      }
    }
    *a1 = v15;
    goto LABEL_34;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
    goto LABEL_32;
  v9 = 52;
LABEL_10:
  WPP_SF_d(v8[7], v9, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, Memory);
LABEL_32:
  FreeEapAttributes(v15);
LABEL_34:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 56, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180021530  mov     [rsp+arg_0], rbx
0x180021535  mov     [rsp+arg_10], rbp
0x18002153a  push    rsi
0x18002153b  push    rdi
0x18002153c  push    r13
0x18002153e  push    r14
0x180021540  push    r15
0x180021542  sub     rsp, 20h
0x180021546  mov     rdi, rdx
0x180021549  mov     [rsp+48h+arg_8], 0
0x180021552  mov     r15, rcx
0x180021555  mov     rcx, cs:WPP_GLOBAL_Control
0x18002155c  lea     r13, WPP_GLOBAL_Control
0x180021563  cmp     rcx, r13
0x180021566  jz      short loc_18002158D
0x180021568  test    dword ptr [rcx+44h], 800h
0x18002156f  jz      short loc_18002158D
0x180021571  mov     rcx, [rcx+38h]
0x180021575  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x18002157c  mov     edx, 32h ; '2'
0x180021581  call    WPP_SF_
0x180021586  mov     rcx, cs:WPP_GLOBAL_Control
0x18002158d  mov     ebp, [rdi]
0x18002158f  test    ebp, ebp
0x180021591  jz      short loc_1800215F4
0x180021593  cmp     qword ptr [rdi+8], 0
0x180021598  jz      short loc_1800215FB
0x18002159a  mov     r9d, 3AAh
0x1800215a0  lea     r8, aCopyeapattribu; "CopyEapAttributes"
0x1800215a7  lea     rdx, [rsp+48h+arg_8]
0x1800215ac  mov     ecx, 10h
0x1800215b1  call    cs:__imp_AllocateMemory
0x1800215b7  mov     ebx, eax
0x1800215b9  test    eax, eax
0x1800215bb  jz      short loc_18002161B
0x1800215bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215c4  cmp     rcx, r13
0x1800215c7  jz      loc_180021766
0x1800215cd  test    byte ptr [rcx+44h], 1
0x1800215d1  jz      loc_180021766
0x1800215d7  mov     edx, 34h ; '4'
0x1800215dc  mov     rcx, [rcx+38h]
0x1800215e0  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x1800215e7  mov     r9d, eax
0x1800215ea  call    WPP_SF_d
0x1800215ef  jmp     loc_180021766
0x1800215f4  cmp     qword ptr [rdi+8], 0
0x1800215f9  jz      short loc_18002159A
0x1800215fb  mov     ebx, 57h ; 'W'
0x180021600  cmp     rcx, r13
0x180021603  jz      loc_180021766
0x180021609  test    byte ptr [rcx+44h], 1
0x18002160d  jz      loc_180021766
0x180021613  lea     edx, [rbx-24h]
0x180021616  jmp     loc_180021756
0x18002161b  mov     rax, [rsp+48h+arg_8]
0x180021620  mov     ecx, [rdi]
0x180021622  mov     [rax], ecx
0x180021624  mov     rax, [rsp+48h+arg_8]
0x180021629  mov     qword ptr [rax+8], 0
0x180021631  cmp     qword ptr [rdi+8], 0
0x180021636  jz      loc_180021772
0x18002163c  mov     rdx, [rsp+48h+arg_8]
0x180021641  lea     r8, aCopyeapattribu; "CopyEapAttributes"
0x180021648  mov     ecx, ebp
0x18002164a  add     rdx, 8
0x18002164e  shl     ecx, 4
0x180021651  mov     r9d, 3B2h
0x180021657  call    cs:__imp_AllocateMemory
0x18002165d  mov     ebx, eax
0x18002165f  test    eax, eax
0x180021661  jz      short loc_180021687
0x180021663  mov     rcx, cs:WPP_GLOBAL_Control
0x18002166a  cmp     rcx, r13
0x18002166d  jz      loc_180021766
0x180021673  test    byte ptr [rcx+44h], 1
0x180021677  jz      loc_180021766
0x18002167d  mov     edx, 35h ; '5'
0x180021682  jmp     loc_1800215DC
0x180021687  xor     r14d, r14d
0x18002168a  cmp     r14d, ebp
0x18002168d  jnb     loc_180021772
0x180021693  mov     rax, [rsp+48h+arg_8]
0x180021698  mov     rdx, [rdi+8]
0x18002169c  mov     esi, r14d
0x18002169f  shl     rsi, 4
0x1800216a3  mov     rcx, [rax+8]
0x1800216a7  mov     eax, [rsi+rdx+4]
0x1800216ab  mov     [rcx+rsi+4], eax
0x1800216af  mov     rax, [rsp+48h+arg_8]
0x1800216b4  mov     rdx, [rdi+8]
0x1800216b8  mov     rcx, [rax+8]
0x1800216bc  mov     eax, [rsi+rdx]
0x1800216bf  mov     [rsi+rcx], eax
0x1800216c2  mov     rax, [rdi+8]
0x1800216c6  mov     ecx, [rsi+rax+4]
0x1800216ca  test    ecx, ecx
0x1800216cc  jz      short loc_18002173C
0x1800216ce  mov     rax, [rsp+48h+arg_8]
0x1800216d3  lea     r8, aCopyeapattribu; "CopyEapAttributes"
0x1800216da  mov     r9d, 3C1h
0x1800216e0  mov     rdx, [rax+8]
0x1800216e4  add     rdx, 8
0x1800216e8  add     rdx, rsi
0x1800216eb  call    cs:__imp_AllocateMemory
0x1800216f1  mov     ebx, eax
0x1800216f3  test    eax, eax
0x1800216f5  jnz     short loc_180021720
0x1800216f7  mov     rax, [rsp+48h+arg_8]
0x1800216fc  mov     rdx, [rdi+8]
0x180021700  mov     rcx, [rax+8]
0x180021704  mov     rdx, [rsi+rdx+8]; Src
0x180021709  mov     r8d, [rcx+rsi+4]; Size
0x18002170e  mov     rcx, [rcx+rsi+8]; void *
0x180021713  call    memcpy_0
0x180021718  inc     r14d
0x18002171b  jmp     loc_18002168A
0x180021720  mov     rcx, cs:WPP_GLOBAL_Control
0x180021727  cmp     rcx, r13
0x18002172a  jz      short loc_180021766
0x18002172c  test    byte ptr [rcx+44h], 1
0x180021730  jz      short loc_180021766
0x180021732  mov     edx, 37h ; '7'
0x180021737  jmp     loc_1800215DC
0x18002173c  mov     ebx, 57h ; 'W'
0x180021741  mov     rcx, cs:WPP_GLOBAL_Control
0x180021748  cmp     rcx, r13
0x18002174b  jz      short loc_180021766
0x18002174d  test    byte ptr [rcx+44h], 1
0x180021751  jz      short loc_180021766
0x180021753  lea     edx, [rbx-21h]
0x180021756  mov     rcx, [rcx+38h]
0x18002175a  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x180021761  call    WPP_SF_
0x180021766  mov     rcx, [rsp+48h+arg_8]
0x18002176b  call    FreeEapAttributes
0x180021770  jmp     short loc_18002177A
0x180021772  mov     rax, [rsp+48h+arg_8]
0x180021777  mov     [r15], rax
0x18002177a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021781  cmp     rcx, r13
0x180021784  jz      short loc_1800217A7
0x180021786  test    dword ptr [rcx+44h], 800h
0x18002178d  jz      short loc_1800217A7
0x18002178f  mov     rcx, [rcx+38h]
0x180021793  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x18002179a  mov     edx, 38h ; '8'
0x18002179f  mov     r9d, ebx
0x1800217a2  call    WPP_SF_D
0x1800217a7  mov     rbp, [rsp+48h+arg_10]
0x1800217ac  mov     eax, ebx
0x1800217ae  mov     rbx, [rsp+48h+arg_0]
0x1800217b3  add     rsp, 20h
0x1800217b7  pop     r15
0x1800217b9  pop     r14
0x1800217bb  pop     r13
0x1800217bd  pop     rdi
0x1800217be  pop     rsi
0x1800217bf  retn
```
