# NCryptCreateProtectionDescriptor

- ea: `0x180015490`
- end: `0x180015765`
- name: `NCryptCreateProtectionDescriptor`
- size: `725`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000382c`

## callees

- `0x18000962c`
- `0x18000d02c`
- `0x18000e120`
- `0x180015490`
- `0x180015c4c`
- `0x18001d0f0`
- `0x18001f145`
- `0x18001f175`
- `0x18001f1b0`
- `0x180020010`

## string_xrefs

- `0x18001555c`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800155a4`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800156ff`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x18001574d`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`

## pseudocode

```c
__int64 __fastcall NCryptCreateProtectionDescriptor(const WCHAR *Src, int a2, _QWORD *a3)
{
  WCHAR *v4; // r14
  unsigned __int64 *v5; // rdi
  int v6; // edx
  unsigned int ProtectionDescriptor; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx
  unsigned int v11; // eax
  size_t v12; // rbx
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  unsigned __int64 *v17; // rax
  unsigned int v18; // eax
  __int64 v19; // [rsp+0h] [rbp-40h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp+0h] BYREF
  __int64 v21; // [rsp+48h] [rbp+8h] BYREF

  v20 = 0;
  v4 = (WCHAR *)Src;
  if ( a3 )
  {
    *a3 = 0;
    if ( Src && *Src )
    {
      if ( (a2 & 0xFFFFFFDE) != 0 )
      {
        ProtectionDescriptor = -2146893815;
        v9 = 296;
        v10 = 2148073481LL;
      }
      else
      {
        v5 = 0;
        if ( (a2 & 1) == 0 )
          goto LABEL_6;
        v11 = NCryptQueryProtectionDescriptorName(Src, 0, &v20);
        ProtectionDescriptor = v11;
        if ( v11 )
        {
          v9 = 315;
          v10 = v11;
        }
        else if ( v20 >= 2 )
        {
          v12 = 2 * v20;
          if ( !(2 * v20)
            || v12 > g_ulMaxStackAllocSize
            || v12 + g_ulAdditionalProbeSize + 8 < v12
            || !(unsigned int)VerifyStackAvailable() )
          {
            goto LABEL_42;
          }
          v13 = v12 + 23;
          if ( v12 + 23 <= v12 + 8 )
            v13 = 0xFFFFFFFFFFFFFF0LL;
          v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
          v15 = alloca(v14);
          v16 = alloca(v14);
          v5 = &v20;
          if ( &v19 == (__int64 *)-64LL || (LODWORD(v20) = 1801679955, (v5 = (unsigned __int64 *)&v21) == 0) )
          {
LABEL_42:
            if ( v12 + 8 >= v12 )
            {
              v17 = (unsigned __int64 *)((__int64 (*)(void))g_pfnAllocate)();
              v5 = v17;
              if ( v17 )
              {
                *(_DWORD *)v17 = 1885431112;
                v5 = v17 + 1;
              }
            }
          }
          if ( v5 )
          {
            memset_0(v5, 0, v12);
            v18 = NCryptQueryProtectionDescriptorName(v4, (LPBYTE)v5, &v20);
            ProtectionDescriptor = v18;
            if ( v18 )
            {
              DebugTraceError(
                v18,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
                345);
              goto LABEL_35;
            }
            v4 = (WCHAR *)v5;
LABEL_6:
            ProtectionDescriptor = I_CreateProtectionDescriptor(v4, (__int64)a3);
            if ( ProtectionDescriptor
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v6,
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
                (unsigned int)"Status",
                ProtectionDescriptor,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
                107);
            }
            if ( !v5 )
              return ProtectionDescriptor;
LABEL_35:
            if ( *((_DWORD *)v5 - 2) == 1885431112 )
              ((void (*)(void))g_pfnFree)();
            return ProtectionDescriptor;
          }
          ProtectionDescriptor = -2146893810;
          v9 = 331;
          v10 = 2148073486LL;
        }
        else
        {
          ProtectionDescriptor = -2146893807;
          v9 = 322;
          v10 = 2148073489LL;
        }
      }
    }
    else
    {
      ProtectionDescriptor = -2146893785;
      v9 = 285;
      v10 = 2148073511LL;
    }
    DebugTraceError(
      v10,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
      v9);
    return ProtectionDescriptor;
  }
  ProtectionDescriptor = -2146893785;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
      18);
  return ProtectionDescriptor;
}

```

## disassembly

```asm
0x180015490  push    rbp
0x180015492  push    rbx
0x180015493  push    rsi
0x180015494  push    rdi
0x180015495  push    r12
0x180015497  push    r14
0x180015499  push    r15
0x18001549b  sub     rsp, 60h
0x18001549f  lea     rbp, [rsp+40h]
0x1800154a4  mov     rax, cs:__security_cookie
0x1800154ab  xor     rax, rbp
0x1800154ae  mov     [rbp+50h+var_40], rax
0x1800154b2  mov     [rbp+50h+var_50], 0
0x1800154ba  mov     r15, r8
0x1800154bd  mov     esi, edx
0x1800154bf  mov     r14, rcx
0x1800154c2  test    r8, r8
0x1800154c5  jz      loc_180015582
0x1800154cb  mov     qword ptr [r8], 0
0x1800154d2  test    rcx, rcx
0x1800154d5  jz      loc_18001573D
0x1800154db  xor     eax, eax
0x1800154dd  cmp     ax, [rcx]
0x1800154e0  jz      loc_18001573D
0x1800154e6  test    edx, 0FFFFFFDEh
0x1800154ec  jnz     loc_1800155D1
0x1800154f2  xor     edi, edi
0x1800154f4  test    sil, 1
0x1800154f8  jnz     loc_1800155E6
0x1800154fe  mov     r9d, esi
0x180015501  mov     [rsp+90h+var_70], r15; __int64
0x180015506  xor     r8d, r8d
0x180015509  xor     edx, edx
0x18001550b  mov     rcx, r14; Src
0x18001550e  call    I_CreateProtectionDescriptor
0x180015513  mov     ebx, eax
0x180015515  test    eax, eax
0x180015517  jnz     short loc_18001553F
0x180015519  test    rdi, rdi
0x18001551c  jnz     loc_180015714
0x180015522  mov     eax, ebx
0x180015524  mov     rcx, [rbp+50h+var_40]
0x180015528  xor     rcx, rbp; StackCookie
0x18001552b  call    __security_check_cookie
0x180015530  lea     rsp, [rbp+20h]
0x180015534  pop     r15
0x180015536  pop     r14
0x180015538  pop     r12
0x18001553a  pop     rdi
0x18001553b  pop     rsi
0x18001553c  pop     rbx
0x18001553d  pop     rbp
0x18001553e  retn
0x18001553f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015546  lea     rax, WPP_GLOBAL_Control
0x18001554d  cmp     rcx, rax
0x180015550  jz      short loc_180015519
0x180015552  test    byte ptr [rcx+1Ch], 1
0x180015556  jz      short loc_180015519
0x180015558  mov     rcx, [rcx+10h]
0x18001555c  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015563  mov     [rsp+90h+var_60], 16Bh
0x18001556b  lea     r9, aStatus; "Status"
0x180015572  mov     [rsp+90h+var_68], r8
0x180015577  mov     dword ptr [rsp+90h+var_70], ebx
0x18001557b  call    WPP_SF_sDsd
0x180015580  jmp     short loc_180015519
0x180015582  mov     ebx, 80090027h
0x180015587  mov     rcx, cs:WPP_GLOBAL_Control
0x18001558e  lea     rax, WPP_GLOBAL_Control
0x180015595  cmp     rcx, rax
0x180015598  jz      short loc_180015522
0x18001559a  test    byte ptr [rcx+1Ch], 1
0x18001559e  jz      short loc_180015522
0x1800155a0  mov     rcx, [rcx+10h]
0x1800155a4  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800155ab  mov     [rsp+90h+var_60], 112h
0x1800155b3  lea     r9, aStatus; "Status"
0x1800155ba  mov     [rsp+90h+var_68], r8
0x1800155bf  mov     dword ptr [rsp+90h+var_70], 80090027h
0x1800155c7  call    WPP_SF_sDsd
0x1800155cc  jmp     loc_180015522
0x1800155d1  mov     ebx, 80090009h
0x1800155d6  mov     r9d, 128h
0x1800155dc  mov     ecx, 80090009h; lpValueName
0x1800155e1  jmp     loc_18001574D
0x1800155e6  and     esi, 0FFFFFFFEh
0x1800155e9  lea     r8, [rbp+50h+var_50]
0x1800155ed  mov     r12d, esi
0x1800155f0  xor     edx, edx; lpData
0x1800155f2  and     r12d, 20h
0x1800155f6  mov     r9d, r12d
0x1800155f9  call    NCryptQueryProtectionDescriptorName
0x1800155fe  mov     ebx, eax
0x180015600  test    eax, eax
0x180015602  jz      short loc_180015611
0x180015604  mov     r9d, 13Bh
0x18001560a  mov     ecx, eax
0x18001560c  jmp     loc_18001574D
0x180015611  mov     rbx, [rbp+50h+var_50]
0x180015615  cmp     rbx, 2
0x180015619  jnb     short loc_180015630
0x18001561b  mov     ebx, 80090011h
0x180015620  mov     r9d, 142h
0x180015626  mov     ecx, 80090011h
0x18001562b  jmp     loc_18001574D
0x180015630  add     rbx, rbx
0x180015633  jz      short loc_180015696
0x180015635  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18001563c  ja      short loc_180015696
0x18001563e  mov     rcx, cs:g_ulAdditionalProbeSize
0x180015645  add     rcx, 8
0x180015649  add     rcx, rbx
0x18001564c  cmp     rcx, rbx
0x18001564f  jb      short loc_180015696
0x180015651  call    VerifyStackAvailable
0x180015656  test    eax, eax
0x180015658  jz      short loc_180015696
0x18001565a  lea     rax, [rbx+8]
0x18001565e  lea     rcx, [rax+0Fh]
0x180015662  cmp     rcx, rax
0x180015665  ja      short loc_180015671
0x180015667  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180015671  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180015675  mov     rax, rcx
0x180015678  call    __chkstk_0
0x18001567d  sub     rsp, rcx
0x180015680  lea     rdi, [rsp+90h+var_50]
0x180015685  test    rdi, rdi
0x180015688  jz      short loc_180015696
0x18001568a  mov     dword ptr [rdi], 6B637453h
0x180015690  add     rdi, 8
0x180015694  jnz     short loc_1800156BD
0x180015696  lea     rcx, [rbx+8]
0x18001569a  cmp     rcx, rbx
0x18001569d  jb      short loc_1800156BD
0x18001569f  mov     rax, cs:g_pfnAllocate
0x1800156a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156ab  mov     rdi, rax
0x1800156ae  test    rax, rax
0x1800156b1  jz      short loc_1800156BD
0x1800156b3  mov     dword ptr [rax], 70616548h
0x1800156b9  add     rdi, 8
0x1800156bd  test    rdi, rdi
0x1800156c0  jnz     short loc_1800156D4
0x1800156c2  mov     ebx, 8009000Eh
0x1800156c7  mov     r9d, 14Bh
0x1800156cd  mov     ecx, 8009000Eh
0x1800156d2  jmp     short loc_18001574D
0x1800156d4  mov     r8, rbx; Size
0x1800156d7  xor     edx, edx; Val
0x1800156d9  mov     rcx, rdi; void *
0x1800156dc  call    memset_0
0x1800156e1  mov     r9d, r12d
0x1800156e4  lea     r8, [rbp+50h+var_50]
0x1800156e8  mov     rdx, rdi; lpData
0x1800156eb  mov     rcx, r14; lpValueName
0x1800156ee  call    NCryptQueryProtectionDescriptorName
0x1800156f3  mov     ebx, eax
0x1800156f5  test    eax, eax
0x1800156f7  jz      short loc_180015735
0x1800156f9  mov     r9d, 159h
0x1800156ff  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015706  lea     rdx, aStatus; "Status"
0x18001570d  mov     ecx, eax
0x18001570f  call    DebugTraceError
0x180015714  lea     rcx, [rdi-8]
0x180015718  cmp     dword ptr [rcx], 70616548h
0x18001571e  jnz     loc_180015522
0x180015724  mov     rax, cs:g_pfnFree
0x18001572b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015730  jmp     loc_180015522
0x180015735  mov     r14, rdi
0x180015738  jmp     loc_1800154FE
0x18001573d  mov     ebx, 80090027h
0x180015742  mov     r9d, 11Dh
0x180015748  mov     ecx, 80090027h
0x18001574d  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015754  lea     rdx, aStatus; "Status"
0x18001575b  call    DebugTraceError
0x180015760  jmp     loc_180015522
```
