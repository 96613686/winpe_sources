# ReadISAKMPObjectsFromRegistry

- ea: `0x180039614`
- end: `0x180039781`
- name: `ReadISAKMPObjectsFromRegistry`
- size: `365`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180039c80`

## callees

- `0x180006f00`
- `0x18000e510`
- `0x180039614`
- `0x18003a668`
- `0x180042c20`
- `0x180042ef8`

## pseudocode

```c
__int64 __fastcall ReadISAKMPObjectsFromRegistry(
        HKEY hKey,
        __int64 a2,
        unsigned __int16 **a3,
        __int64 a4,
        _QWORD *a5,
        _DWORD *a6)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  _QWORD *v14; // rdi
  __int64 result; // rax
  SIZE_T v16; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17[8]; // [rsp+38h] [rbp-40h] BYREF

  v17[0] = 0;
  v16 = 0;
  *a5 = 0;
  *a6 = 0;
  v9 = NsuSizeTMultiply(1, 8, &v16);
  v10 = v9;
  if ( v9 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_16;
    v12 = 27;
    v13 = v9;
    goto LABEL_5;
  }
  v14 = IpsecAllocMem(v16);
  if ( !v14 )
  {
    v10 = 14;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_16;
    v12 = 28;
    v13 = 14;
LABEL_5:
    WPP_SF_d(v11[2], v12, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v13);
    goto LABEL_16;
  }
  if ( !(unsigned int)UnMarshallRegistryISAKMPObject(hKey, a2, *a3, 1, v17) )
  {
    *v14 = v17[0];
    result = 0;
    *a5 = v14;
    *a6 = 1;
    return result;
  }
  v10 = 13;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, 13);
  FreeIpsecISAKMPObjects(v14);
LABEL_16:
  *a5 = 0;
  result = v10;
  *a6 = 0;
  return result;
}

```

## disassembly

```asm
0x180039614  push    rbx
0x180039616  push    rbp
0x180039617  push    rsi
0x180039618  push    rdi
0x180039619  push    r12
0x18003961b  push    r14
0x18003961d  push    r15
0x18003961f  sub     rsp, 40h
0x180039623  mov     rsi, [rsp+78h+arg_20]
0x18003962b  mov     rbp, rdx
0x18003962e  mov     r14, [rsp+78h+arg_28]
0x180039636  mov     edx, 8
0x18003963b  mov     r15, r8
0x18003963e  mov     [rsp+78h+var_40], 0
0x180039647  mov     r12, rcx
0x18003964a  mov     [rsp+78h+var_48], 0
0x180039653  lea     r8, [rsp+78h+var_48]
0x180039658  mov     qword ptr [rsi], 0
0x18003965f  lea     ecx, [rdx-7]
0x180039662  mov     dword ptr [r14], 0
0x180039669  call    NsuSizeTMultiply
0x18003966e  mov     ebx, eax
0x180039670  test    eax, eax
0x180039672  jz      short loc_1800396B2
0x180039674  mov     rcx, cs:WPP_GLOBAL_Control
0x18003967b  lea     rdx, WPP_GLOBAL_Control
0x180039682  cmp     rcx, rdx
0x180039685  jz      loc_180039762
0x18003968b  test    byte ptr [rcx+1Ch], 10h
0x18003968f  jz      loc_180039762
0x180039695  mov     edx, 1Bh
0x18003969a  mov     r9d, eax
0x18003969d  mov     rcx, [rcx+10h]
0x1800396a1  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x1800396a8  call    WPP_SF_d
0x1800396ad  jmp     loc_180039762
0x1800396b2  mov     rcx, [rsp+78h+var_48]
0x1800396b7  call    IpsecAllocMem
0x1800396bc  mov     rdi, rax
0x1800396bf  test    rax, rax
0x1800396c2  jnz     short loc_1800396EC
0x1800396c4  lea     ebx, [rax+0Eh]
0x1800396c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800396ce  lea     rdx, WPP_GLOBAL_Control
0x1800396d5  cmp     rcx, rdx
0x1800396d8  jz      loc_180039762
0x1800396de  test    byte ptr [rcx+1Ch], 10h
0x1800396e2  jz      short loc_180039762
0x1800396e4  lea     edx, [rax+1Ch]
0x1800396e7  mov     r9d, ebx
0x1800396ea  jmp     short loc_18003969D
0x1800396ec  mov     r8, [r15]
0x1800396ef  lea     rax, [rsp+78h+var_40]
0x1800396f4  mov     r9d, 1
0x1800396fa  mov     [rsp+78h+var_58], rax; __int64
0x1800396ff  mov     rdx, rbp
0x180039702  mov     rcx, r12; hKey
0x180039705  call    UnMarshallRegistryISAKMPObject
0x18003970a  test    eax, eax
0x18003970c  jnz     short loc_180039724
0x18003970e  mov     rax, [rsp+78h+var_40]
0x180039713  mov     [rdi], rax
0x180039716  xor     eax, eax
0x180039718  mov     [rsi], rdi
0x18003971b  mov     dword ptr [r14], 1
0x180039722  jmp     short loc_180039772
0x180039724  mov     ebx, 0Dh
0x180039729  mov     rcx, cs:WPP_GLOBAL_Control
0x180039730  lea     rdx, WPP_GLOBAL_Control
0x180039737  cmp     rcx, rdx
0x18003973a  jz      short loc_180039758
0x18003973c  test    byte ptr [rcx+1Ch], 10h
0x180039740  jz      short loc_180039758
0x180039742  mov     rcx, [rcx+10h]
0x180039746  lea     edx, [rbx+10h]
0x180039749  mov     r9d, ebx
0x18003974c  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x180039753  call    WPP_SF_d
0x180039758  xor     edx, edx
0x18003975a  mov     rcx, rdi; lpMem
0x18003975d  call    FreeIpsecISAKMPObjects
0x180039762  mov     qword ptr [rsi], 0
0x180039769  mov     eax, ebx
0x18003976b  mov     dword ptr [r14], 0
0x180039772  add     rsp, 40h
0x180039776  pop     r15
0x180039778  pop     r14
0x18003977a  pop     r12
0x18003977c  pop     rdi
0x18003977d  pop     rsi
0x18003977e  pop     rbp
0x18003977f  pop     rbx
0x180039780  retn
```
