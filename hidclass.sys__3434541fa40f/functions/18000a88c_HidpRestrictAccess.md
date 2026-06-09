# HidpRestrictAccess

- ea: `0x18000a88c`
- end: `0x18000ac63`
- name: `HidpRestrictAccess`
- size: `983`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800405e4`

## callees

- `0x180009a78`
- `0x18000a430`
- `0x18000a80c`
- `0x18000a88c`
- `0x18000c250`
- `0x18000cc90`
- `0x180013860`

## import_xrefs

- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x18000aa82`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x18000aa82`

## pseudocode

```c
__int64 __fastcall HidpRestrictAccess(__int64 a1)
{
  __int64 v1; // r13
  __int64 v3; // rdx
  int v4; // r15d
  __int64 HidclassCollection; // rax
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 v8; // r8
  unsigned __int16 *CollectionDesc; // rax
  __int64 v10; // r8
  unsigned int v11; // ecx
  bool v12; // di
  char v13; // r13
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  bool v16; // zf
  unsigned int v17; // ecx
  bool v18; // zf
  int FunctionDriverType; // ebp
  bool v20; // r10
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rdx
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rax
  __int16 v31; // [rsp+30h] [rbp-78h]
  __int64 v32; // [rsp+40h] [rbp-68h]
  int v33; // [rsp+48h] [rbp-60h]
  __int64 v34; // [rsp+50h] [rbp-58h]
  char v35; // [rsp+58h] [rbp-50h]
  __int128 v36[4]; // [rsp+60h] [rbp-48h] BYREF
  int v37; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v38; // [rsp+B8h] [rbp+10h]
  __int64 v39; // [rsp+C0h] [rbp+18h]

  v1 = *(_QWORD *)(a1 + 64);
  v3 = *(unsigned int *)(a1 + 8);
  v4 = 0;
  v37 = 0;
  v38 = v1;
  HidclassCollection = GetHidclassCollection(v1 + 32, v3);
  v6 = *(unsigned int *)(a1 + 8);
  v7 = HidclassCollection;
  v39 = HidclassCollection;
  CollectionDesc = (unsigned __int16 *)GetCollectionDesc(v1 + 32, v6, v8);
  if ( v7 && CollectionDesc )
  {
    v11 = *CollectionDesc;
    v12 = 1;
    v13 = 0;
    if ( v11 > 0xD )
    {
      v21 = v11 - 32;
      if ( !v21 )
        goto LABEL_16;
      v22 = v21 - 108;
      if ( !v22 )
        goto LABEL_16;
      v17 = v22 - 1;
      v16 = v17 == 0;
    }
    else
    {
      if ( v11 == 13 || !*CollectionDesc )
        goto LABEL_16;
      v14 = v11 - 1;
      if ( !v14 )
      {
        switch ( CollectionDesc[1] )
        {
          case 2u:
            goto LABEL_16;
          case 4u:
          case 5u:
            v13 = 1;
            goto LABEL_16;
          case 6u:
          case 7u:
LABEL_16:
            FunctionDriverType = 0;
            v20 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
            if ( v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v23 = *(_QWORD *)(a1 + 64);
              v24 = *(_QWORD *)(v23 + 32);
              LOBYTE(v23) = v20;
              LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_qdq(
                WPP_GLOBAL_Control->AttachedDevice,
                v23,
                v10,
                *(_QWORD *)(v38 + 704),
                4,
                2,
                11,
                (__int64)WPP_b44b9c582a6d3a011072db7b2d15a10e_Traceguids,
                v24,
                *(_DWORD *)(a1 + 8),
                *(_QWORD *)(a1 + 48));
            }
            if ( !v13 )
              return (unsigned int)FunctionDriverType;
            goto LABEL_35;
        }
        v18 = CollectionDesc[1] == 128;
LABEL_25:
        if ( !v18 )
        {
          FunctionDriverType = HidpGetFunctionDriverType(a1, &v37, v10, WPP_b44b9c582a6d3a011072db7b2d15a10e_Traceguids);
          if ( FunctionDriverType < 0 )
            return (unsigned int)FunctionDriverType;
          if ( !*(_DWORD *)(a1 + 344) )
          {
            FunctionDriverType = HidpGetFilterDriverTypes(a1, &v37);
            if ( FunctionDriverType < 0 )
              return (unsigned int)FunctionDriverType;
          }
          v4 = v37;
LABEL_35:
          LOBYTE(v37) = -(v4 != 0);
          v36[0] = *(_OWORD *)(v39 + 256);
          FunctionDriverType = IoSetDeviceInterfacePropertyData(
                                 v36,
                                 &DEVPKEY_DeviceInterface_Restricted,
                                 0,
                                 0,
                                 17,
                                 1,
                                 &v37);
          if ( FunctionDriverType >= 0 )
          {
            if ( v4 )
            {
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
              {
                v12 = 0;
              }
              if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v28 = *(_QWORD *)(a1 + 64);
                v29 = *(_QWORD *)(v28 + 32);
                LOBYTE(v28) = v12;
                LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                WPP_RECORDER_AND_TRACE_SF_qdqL(
                  WPP_GLOBAL_Control->AttachedDevice,
                  v28,
                  v10,
                  *(_QWORD *)(v38 + 704),
                  4,
                  2,
                  13,
                  (__int64)WPP_b44b9c582a6d3a011072db7b2d15a10e_Traceguids,
                  v29,
                  *(_DWORD *)(a1 + 8),
                  *(_QWORD *)(a1 + 48),
                  v4);
              }
            }
          }
          else
          {
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              v12 = 0;
            }
            LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v35 = FunctionDriverType;
              v34 = *(_QWORD *)(a1 + 48);
              v33 = *(_DWORD *)(a1 + 8);
              v32 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 32LL);
              v31 = 12;
              v27 = *(_QWORD *)(v38 + 704);
LABEL_59:
              LOBYTE(v25) = v12;
              WPP_RECORDER_AND_TRACE_SF_qdqL(
                v26->AttachedDevice,
                v25,
                v10,
                v27,
                2,
                2,
                v31,
                (__int64)WPP_b44b9c582a6d3a011072db7b2d15a10e_Traceguids,
                v32,
                v33,
                v34,
                v35);
              return (unsigned int)FunctionDriverType;
            }
          }
          return (unsigned int)FunctionDriverType;
        }
        goto LABEL_16;
      }
      v15 = v14 - 6;
      if ( !v15 )
        goto LABEL_16;
      v17 = v15 - 4;
      v16 = v17 == 0;
    }
    if ( v16 )
      goto LABEL_16;
    v18 = v17 == 1;
    goto LABEL_25;
  }
  FunctionDriverType = -1073741438;
  v26 = WPP_GLOBAL_Control;
  v12 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
     && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v25 = *(_QWORD *)(a1 + 64);
    v27 = *(_QWORD *)(v1 + 704);
    v35 = -126;
    v34 = *(_QWORD *)(a1 + 48);
    v33 = *(_DWORD *)(a1 + 8);
    v32 = *(_QWORD *)(v25 + 32);
    v31 = 10;
    goto LABEL_59;
  }
  return (unsigned int)FunctionDriverType;
}

```

## disassembly

```asm
0x18000a88c  mov     rax, rsp
0x18000a88f  mov     [rax+20h], rbx
0x18000a893  push    rbp
0x18000a894  push    rsi
0x18000a895  push    rdi
0x18000a896  push    r12
0x18000a898  push    r13
0x18000a89a  push    r14
0x18000a89c  push    r15
0x18000a89e  sub     rsp, 70h
0x18000a8a2  mov     r13, [rcx+40h]
0x18000a8a6  mov     rsi, rcx
0x18000a8a9  mov     edx, [rcx+8]
0x18000a8ac  xor     r15d, r15d
0x18000a8af  mov     [rax+8], r15d
0x18000a8b3  mov     [rsp+0A8h+arg_8], r13
0x18000a8bb  lea     rcx, [r13+20h]
0x18000a8bf  call    GetHidclassCollection
0x18000a8c4  mov     edx, [rsi+8]
0x18000a8c7  lea     rcx, [r13+20h]
0x18000a8cb  mov     rdi, rax
0x18000a8ce  mov     [rsp+0A8h+arg_10], rax
0x18000a8d6  call    GetCollectionDesc
0x18000a8db  mov     rdx, rax
0x18000a8de  test    rdi, rdi
0x18000a8e1  jz      loc_18000ABAC
0x18000a8e7  test    rax, rax
0x18000a8ea  jz      loc_18000ABAC
0x18000a8f0  movzx   ecx, word ptr [rax]
0x18000a8f3  lea     edi, [r15+1]
0x18000a8f7  lea     eax, [rdi+0Ch]
0x18000a8fa  xor     r13b, r13b
0x18000a8fd  lea     r14, WPP_GLOBAL_Control
0x18000a904  lea     r12, WPP_RECORDER_INITIALIZED
0x18000a90b  lea     r9, WPP_b44b9c582a6d3a011072db7b2d15a10e_Traceguids
0x18000a912  lea     ebx, [rdi+1]
0x18000a915  cmp     ecx, eax
0x18000a917  ja      short loc_18000A96D
0x18000a919  jz      short loc_18000A94D
0x18000a91b  test    ecx, ecx
0x18000a91d  jz      short loc_18000A94D
0x18000a91f  sub     ecx, edi
0x18000a921  jz      short loc_18000A92D
0x18000a923  sub     ecx, 6
0x18000a926  jz      short loc_18000A94D
0x18000a928  sub     ecx, 4
0x18000a92b  jmp     short loc_18000A979
0x18000a92d  movzx   ecx, word ptr [rdx+2]
0x18000a931  sub     ecx, ebx
0x18000a933  jz      short loc_18000A94D
0x18000a935  sub     ecx, ebx
0x18000a937  jz      short loc_18000A94A
0x18000a939  sub     ecx, edi
0x18000a93b  jz      short loc_18000A94A
0x18000a93d  sub     ecx, edi
0x18000a93f  jz      short loc_18000A94D
0x18000a941  sub     ecx, edi
0x18000a943  jz      short loc_18000A94D
0x18000a945  cmp     ecx, 79h ; 'y'
0x18000a948  jmp     short loc_18000A97D
0x18000a94a  mov     r13b, dil
0x18000a94d  xor     ebp, ebp
0x18000a94f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a956  cmp     rcx, r14
0x18000a959  jz      short loc_18000A9C6
0x18000a95b  mov     eax, [rcx+2Ch]
0x18000a95e  test    bl, al
0x18000a960  jz      short loc_18000A9C6
0x18000a962  cmp     byte ptr [rcx+29h], 4
0x18000a966  jb      short loc_18000A9C6
0x18000a968  mov     r10b, dil
0x18000a96b  jmp     short loc_18000A9C9
0x18000a96d  sub     ecx, 20h ; ' '
0x18000a970  jz      short loc_18000A94D
0x18000a972  sub     ecx, 6Ch ; 'l'
0x18000a975  jz      short loc_18000A94D
0x18000a977  sub     ecx, edi
0x18000a979  jz      short loc_18000A94D
0x18000a97b  cmp     ecx, edi
0x18000a97d  jz      short loc_18000A94D
0x18000a97f  lea     rdx, [rsp+0A8h+arg_0]
0x18000a987  mov     rcx, rsi
0x18000a98a  call    HidpGetFunctionDriverType
0x18000a98f  mov     ebp, eax
0x18000a991  test    eax, eax
0x18000a993  js      loc_18000AC48
0x18000a999  cmp     [rsi+158h], r15d
0x18000a9a0  jnz     short loc_18000A9BC
0x18000a9a2  lea     rdx, [rsp+0A8h+arg_0]
0x18000a9aa  mov     rcx, rsi
0x18000a9ad  call    HidpGetFilterDriverTypes
0x18000a9b2  mov     ebp, eax
0x18000a9b4  test    eax, eax
0x18000a9b6  js      loc_18000AC48
0x18000a9bc  mov     r15d, [rsp+0A8h+arg_0]
0x18000a9c4  jmp     short loc_18000AA34
0x18000a9c6  xor     r10b, r10b
0x18000a9c9  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000a9d0  setnz   r8b
0x18000a9d4  test    r10b, r10b
0x18000a9d7  jnz     short loc_18000A9DE
0x18000a9d9  test    r8b, r8b
0x18000a9dc  jz      short loc_18000AA2B
0x18000a9de  mov     rax, [rsi+30h]
0x18000a9e2  mov     rdx, [rsi+40h]
0x18000a9e6  mov     rcx, [rcx+18h]
0x18000a9ea  mov     [rsp+0A8h+var_58], rax
0x18000a9ef  mov     eax, [rsi+8]
0x18000a9f2  mov     [rsp+0A8h+var_60], eax
0x18000a9f6  mov     rax, [rdx+20h]
0x18000a9fa  mov     dl, r10b
0x18000a9fd  mov     [rsp+0A8h+var_68], rax
0x18000aa02  mov     [rsp+0A8h+var_70], r9
0x18000aa07  mov     r9, [rsp+0A8h+arg_8]
0x18000aa0f  mov     word ptr [rsp+0A8h+var_78], 0Bh
0x18000aa16  mov     [rsp+0A8h+var_80], ebx
0x18000aa1a  mov     byte ptr [rsp+0A8h+var_88], 4
0x18000aa1f  mov     r9, [r9+2C0h]
0x18000aa26  call    WPP_RECORDER_AND_TRACE_SF_qdq
0x18000aa2b  test    r13b, r13b
0x18000aa2e  jz      loc_18000AC48
0x18000aa34  xor     eax, eax
0x18000aa36  lea     rdx, DEVPKEY_DeviceInterface_Restricted
0x18000aa3d  cmp     eax, r15d
0x18000aa40  lea     rcx, [rsp+0A8h+var_48]
0x18000aa45  sbb     al, al
0x18000aa47  xor     r9d, r9d
0x18000aa4a  mov     byte ptr [rsp+0A8h+arg_0], al
0x18000aa51  xor     r8d, r8d
0x18000aa54  mov     rax, [rsp+0A8h+arg_10]
0x18000aa5c  movups  xmm0, xmmword ptr [rax+100h]
0x18000aa63  lea     rax, [rsp+0A8h+arg_0]
0x18000aa6b  mov     [rsp+0A8h+var_78], rax
0x18000aa70  mov     [rsp+0A8h+var_80], edi
0x18000aa74  mov     [rsp+0A8h+var_88], 11h
0x18000aa7c  movdqu  [rsp+0A8h+var_48], xmm0
0x18000aa82  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x18000aa89  nop     dword ptr [rax+rax+00h]
0x18000aa8e  mov     ebp, eax
0x18000aa90  test    eax, eax
0x18000aa92  jns     short loc_18000AB10
0x18000aa94  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa9b  cmp     rcx, r14
0x18000aa9e  jz      short loc_18000AAAC
0x18000aaa0  mov     eax, [rcx+2Ch]
0x18000aaa3  test    bl, al
0x18000aaa5  jz      short loc_18000AAAC
0x18000aaa7  cmp     [rcx+29h], bl
0x18000aaaa  jnb     short loc_18000AAAF
0x18000aaac  xor     dil, dil
0x18000aaaf  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000aab6  setnz   r8b
0x18000aaba  test    dil, dil
0x18000aabd  jnz     short loc_18000AAC8
0x18000aabf  test    r8b, r8b
0x18000aac2  jz      loc_18000AC48
0x18000aac8  mov     rax, [rsi+30h]
0x18000aacc  mov     r10, [rsi+40h]
0x18000aad0  mov     dword ptr [rsp+0A8h+var_50], ebp
0x18000aad4  mov     [rsp+0A8h+var_58], rax
0x18000aad9  mov     eax, [rsi+8]
0x18000aadc  mov     [rsp+0A8h+var_60], eax
0x18000aae0  mov     rax, [r10+20h]
0x18000aae4  mov     [rsp+0A8h+var_68], rax
0x18000aae9  lea     rax, WPP_b44b9c582a6d3a011072db7b2d15a10e_Traceguids
0x18000aaf0  mov     [rsp+0A8h+var_70], rax
0x18000aaf5  mov     rax, [rsp+0A8h+arg_8]
0x18000aafd  mov     word ptr [rsp+0A8h+var_78], 0Ch
0x18000ab04  mov     r9, [rax+2C0h]
0x18000ab0b  jmp     loc_18000AC34
0x18000ab10  test    r15d, r15d
0x18000ab13  jz      loc_18000AC48
0x18000ab19  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab20  cmp     rcx, r14
0x18000ab23  jz      short loc_18000AB32
0x18000ab25  mov     eax, [rcx+2Ch]
0x18000ab28  test    bl, al
0x18000ab2a  jz      short loc_18000AB32
0x18000ab2c  cmp     byte ptr [rcx+29h], 4
0x18000ab30  jnb     short loc_18000AB35
0x18000ab32  xor     dil, dil
0x18000ab35  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000ab3c  setnz   r8b
0x18000ab40  test    dil, dil
0x18000ab43  jnz     short loc_18000AB4E
0x18000ab45  test    r8b, r8b
0x18000ab48  jz      loc_18000AC48
0x18000ab4e  mov     rax, [rsi+30h]
0x18000ab52  mov     rdx, [rsi+40h]
0x18000ab56  mov     rcx, [rcx+18h]
0x18000ab5a  mov     dword ptr [rsp+0A8h+var_50], r15d
0x18000ab5f  mov     [rsp+0A8h+var_58], rax
0x18000ab64  mov     eax, [rsi+8]
0x18000ab67  mov     [rsp+0A8h+var_60], eax
0x18000ab6b  mov     rax, [rdx+20h]
0x18000ab6f  mov     dl, dil
0x18000ab72  mov     [rsp+0A8h+var_68], rax
0x18000ab77  lea     rax, WPP_b44b9c582a6d3a011072db7b2d15a10e_Traceguids
0x18000ab7e  mov     [rsp+0A8h+var_70], rax
0x18000ab83  mov     rax, [rsp+0A8h+arg_8]
0x18000ab8b  mov     word ptr [rsp+0A8h+var_78], 0Dh
0x18000ab92  mov     [rsp+0A8h+var_80], ebx
0x18000ab96  mov     byte ptr [rsp+0A8h+var_88], 4
0x18000ab9b  mov     r9, [rax+2C0h]
0x18000aba2  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x18000aba7  jmp     loc_18000AC48
0x18000abac  mov     ebp, 0C0000182h
0x18000abb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abb8  lea     r14, WPP_GLOBAL_Control
0x18000abbf  mov     ebx, 2
0x18000abc4  cmp     rcx, r14
0x18000abc7  jz      short loc_18000ABDA
0x18000abc9  mov     eax, [rcx+2Ch]
0x18000abcc  test    bl, al
0x18000abce  jz      short loc_18000ABDA
0x18000abd0  cmp     [rcx+29h], bl
0x18000abd3  jb      short loc_18000ABDA
0x18000abd5  lea     edi, [rbx-1]
0x18000abd8  jmp     short loc_18000ABDD
0x18000abda  xor     dil, dil
0x18000abdd  lea     r12, WPP_RECORDER_INITIALIZED
0x18000abe4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000abeb  setnz   r8b
0x18000abef  test    dil, dil
0x18000abf2  jnz     short loc_18000ABF9
0x18000abf4  test    r8b, r8b
0x18000abf7  jz      short loc_18000AC48
0x18000abf9  mov     rax, [rsi+30h]
0x18000abfd  mov     rdx, [rsi+40h]
0x18000ac01  mov     r9, [r13+2C0h]
0x18000ac08  mov     dword ptr [rsp+0A8h+var_50], ebp
0x18000ac0c  mov     [rsp+0A8h+var_58], rax
0x18000ac11  mov     eax, [rsi+8]
0x18000ac14  mov     [rsp+0A8h+var_60], eax
0x18000ac18  mov     rax, [rdx+20h]
0x18000ac1c  mov     [rsp+0A8h+var_68], rax
0x18000ac21  lea     rax, WPP_b44b9c582a6d3a011072db7b2d15a10e_Traceguids
0x18000ac28  mov     [rsp+0A8h+var_70], rax
0x18000ac2d  mov     word ptr [rsp+0A8h+var_78], 0Ah
0x18000ac34  mov     rcx, [rcx+18h]
0x18000ac38  mov     dl, dil
0x18000ac3b  mov     [rsp+0A8h+var_80], ebx
0x18000ac3f  mov     byte ptr [rsp+0A8h+var_88], bl
0x18000ac43  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x18000ac48  mov     rbx, [rsp+0A8h+arg_18]
0x18000ac50  mov     eax, ebp
0x18000ac52  add     rsp, 70h
0x18000ac56  pop     r15
0x18000ac58  pop     r14
0x18000ac5a  pop     r13
0x18000ac5c  pop     r12
0x18000ac5e  pop     rdi
0x18000ac5f  pop     rsi
0x18000ac60  pop     rbp
0x18000ac61  retn
```
