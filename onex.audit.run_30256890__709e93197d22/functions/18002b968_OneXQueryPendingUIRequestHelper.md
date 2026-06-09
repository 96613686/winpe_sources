# OneXQueryPendingUIRequestHelper

- ea: `0x18002b968`
- end: `0x18002baef`
- name: `OneXQueryPendingUIRequestHelper`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002cae0`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x180019cd0`
- `0x18001d108`
- `0x1800214f0`
- `0x18002b968`

## import_xrefs

- `MobileNetworking!AllocateAndCopyPointerData` at `0x18002ba3a`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x18002ba3a`

## pseudocode

```c
__int64 __fastcall OneXQueryPendingUIRequestHelper(__int64 a1, _DWORD *a2, unsigned int *a3, _QWORD *a4)
{
  unsigned int v4; // esi
  _QWORD *v9; // rcx
  int v10; // ebp
  unsigned int *v11; // rbx
  unsigned int v12; // edi
  int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rax
  __int64 v17; // [rsp+80h] [rbp+8h] BYREF

  v4 = *(_DWORD *)(a1 + 20);
  v17 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  v10 = *(_DWORD *)(a1 + 2608);
  v11 = *(unsigned int **)(a1 + 2616);
  if ( !v11 )
  {
    v12 = 0;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 8) != 0 )
      WPP_SF_d(v9[7], 21, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v4);
    goto LABEL_17;
  }
  v12 = *v11;
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 8) != 0 )
    WPP_SF_ddd(v9[7], 19, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v4, v12, v10);
  if ( (byte_18003DF42 & 8) != 0 )
    McTemplateU0qqq_EtwEventWriteTransfer((_DWORD)v9, (unsigned int)PendingUIRequest, v4, v10, v12);
  v13 = AllocateAndCopyPointerData(&v17, v11, v12);
  LODWORD(v11) = v13;
  if ( !v13 )
  {
LABEL_17:
    v15 = v17;
    *a2 = v10;
    *a3 = v12;
    *a4 = v15;
    goto LABEL_18;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v4, v13);
LABEL_18:
    v14 = WPP_GLOBAL_Control;
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 17) & 0x800) != 0 )
    WPP_SF_D(v14[7], 22, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002b968  mov     rax, rsp
0x18002b96b  push    rbx
0x18002b96c  push    rbp
0x18002b96d  push    rsi
0x18002b96e  push    rdi
0x18002b96f  push    r12
0x18002b971  push    r13
0x18002b973  push    r14
0x18002b975  push    r15
0x18002b977  sub     rsp, 38h
0x18002b97b  mov     esi, [rcx+14h]
0x18002b97e  mov     r14, r9
0x18002b981  mov     r15, r8
0x18002b984  mov     qword ptr [rax+8], 0
0x18002b98c  mov     r12, rdx
0x18002b98f  mov     rbx, rcx
0x18002b992  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b999  lea     r13, WPP_GLOBAL_Control
0x18002b9a0  cmp     rcx, r13
0x18002b9a3  jz      short loc_18002B9CA
0x18002b9a5  test    dword ptr [rcx+44h], 800h
0x18002b9ac  jz      short loc_18002B9CA
0x18002b9ae  mov     rcx, [rcx+38h]
0x18002b9b2  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18002b9b9  mov     edx, 12h
0x18002b9be  call    WPP_SF_
0x18002b9c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9ca  mov     ebp, [rbx+0A30h]
0x18002b9d0  mov     rbx, [rbx+0A38h]
0x18002b9d7  test    rbx, rbx
0x18002b9da  jz      loc_18002BA7A
0x18002b9e0  mov     edi, [rbx]
0x18002b9e2  cmp     rcx, r13
0x18002b9e5  jz      short loc_18002BA0D
0x18002b9e7  test    byte ptr [rcx+44h], 8
0x18002b9eb  jz      short loc_18002BA0D
0x18002b9ed  mov     rcx, [rcx+38h]
0x18002b9f1  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18002b9f8  mov     edx, 13h
0x18002b9fd  mov     [rsp+78h+var_50], ebp
0x18002ba01  mov     r9d, esi
0x18002ba04  mov     [rsp+78h+var_58], edi
0x18002ba08  call    WPP_SF_ddd
0x18002ba0d  test    cs:byte_18003DF42, 8
0x18002ba14  jz      short loc_18002BA2C
0x18002ba16  mov     r9d, ebp
0x18002ba19  mov     [rsp+78h+var_58], edi
0x18002ba1d  mov     r8d, esi
0x18002ba20  lea     rdx, PendingUIRequest
0x18002ba27  call    McTemplateU0qqq_EtwEventWriteTransfer
0x18002ba2c  mov     r8d, edi
0x18002ba2f  lea     rcx, [rsp+78h+arg_0]
0x18002ba37  mov     rdx, rbx
0x18002ba3a  call    cs:__imp_AllocateAndCopyPointerData
0x18002ba40  mov     ebx, eax
0x18002ba42  test    eax, eax
0x18002ba44  jz      short loc_18002BA9D
0x18002ba46  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba4d  cmp     rcx, r13
0x18002ba50  jz      loc_18002BADC
0x18002ba56  test    byte ptr [rcx+44h], 1
0x18002ba5a  jz      short loc_18002BAB6
0x18002ba5c  mov     rcx, [rcx+38h]
0x18002ba60  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18002ba67  mov     edx, 14h
0x18002ba6c  mov     [rsp+78h+var_58], eax
0x18002ba70  mov     r9d, esi
0x18002ba73  call    WPP_SF_dd
0x18002ba78  jmp     short loc_18002BAAF
0x18002ba7a  xor     edi, edi
0x18002ba7c  cmp     rcx, r13
0x18002ba7f  jz      short loc_18002BA9D
0x18002ba81  test    byte ptr [rcx+44h], 8
0x18002ba85  jz      short loc_18002BA9D
0x18002ba87  mov     rcx, [rcx+38h]
0x18002ba8b  lea     edx, [rdi+15h]
0x18002ba8e  mov     r9d, esi
0x18002ba91  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18002ba98  call    WPP_SF_d
0x18002ba9d  mov     rax, [rsp+78h+arg_0]
0x18002baa5  mov     [r12], ebp
0x18002baa9  mov     [r15], edi
0x18002baac  mov     [r14], rax
0x18002baaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bab6  cmp     rcx, r13
0x18002bab9  jz      short loc_18002BADC
0x18002babb  test    dword ptr [rcx+44h], 800h
0x18002bac2  jz      short loc_18002BADC
0x18002bac4  mov     rcx, [rcx+38h]
0x18002bac8  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18002bacf  mov     edx, 16h
0x18002bad4  mov     r9d, ebx
0x18002bad7  call    WPP_SF_D
0x18002badc  mov     eax, ebx
0x18002bade  add     rsp, 38h
0x18002bae2  pop     r15
0x18002bae4  pop     r14
0x18002bae6  pop     r13
0x18002bae8  pop     r12
0x18002baea  pop     rdi
0x18002baeb  pop     rsi
0x18002baec  pop     rbp
0x18002baed  pop     rbx
0x18002baee  retn
```
