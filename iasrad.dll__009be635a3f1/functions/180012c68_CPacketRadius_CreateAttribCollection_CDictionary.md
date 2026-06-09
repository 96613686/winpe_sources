# CPacketRadius::CreateAttribCollection(CDictionary *)

- ea: `0x180012c68`
- end: `0x18001309b`
- name: `?CreateAttribCollection@CPacketRadius@@AEAAJPEAVCDictionary@@@Z`
- size: `1075`
- prototype: `__int64 __fastcall(CPacketRadius *__hidden this, struct CDictionary *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013f90`

## callees

- `0x1800094e4`
- `0x180012c68`
- `0x1800130a4`
- `0x18001312c`
- `0x1800131b8`
- `0x180013808`
- `0x1800138c8`
- `0x180013a98`
- `0x18001d31c`
- `0x18002ada0`
- `0x18002af04`
- `0x18002e202`
- `0x18002e230`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013054`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001306f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013054`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001306f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012cb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012d2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012cb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012d2f`

## pseudocode

```c
__int64 __fastcall CPacketRadius::CreateAttribCollection(CPacketRadius *this, struct CDictionary *a2)
{
  __int64 v3; // r14
  __int64 v4; // rbp
  LPVOID v5; // rax
  _BYTE *v6; // rsi
  __int64 v7; // rdx
  signed int v8; // ebx
  __int64 v9; // r8
  bool v10; // sf
  char *v11; // r14
  __int64 i; // r15
  _QWORD *v13; // r13
  char v14; // al
  _DWORD *v15; // rdx
  _DWORD *v16; // rbx
  _DWORD *v17; // rcx
  __int64 j; // r14
  void *v19; // rcx
  _BYTE v22[512]; // [rsp+40h] [rbp-258h] BYREF

  memset_0(v22, 0, sizeof(v22));
  v3 = *((_QWORD *)this + 3);
  v4 = (unsigned int)(*((_DWORD *)this + 22) + 8);
  v5 = CoTaskMemAlloc(16 * v4);
  *((_QWORD *)this + 2) = v5;
  if ( !v5 )
  {
    v6 = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_7;
    }
    WppDbgPrint("Unable to allocate memory for Attribute position array while creating attribute collection");
    v7 = 12;
LABEL_6:
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_680dfa5530f83761685653fb6ea5f689_Traceguids, "NPSRAD");
LABEL_7:
    v8 = -2147024882;
    goto LABEL_44;
  }
  if ( (unsigned int)v4 <= 0x40 )
  {
    v6 = v22;
  }
  else
  {
    v6 = CoTaskMemAlloc(8 * v4);
    if ( !v6 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      {
        goto LABEL_7;
      }
      WppDbgPrint("Unable to allocate memory for Attribute array while creating attribute collection");
      v7 = 13;
      goto LABEL_6;
    }
  }
  v8 = IASAttributeAlloc((unsigned int)v4, v6);
  if ( !v8 )
  {
    v11 = (char *)(v3 + 20);
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 22); i = (unsigned int)(i + 1) )
    {
      v13 = &v6[8 * i];
      v8 = CPacketRadius::FillInAttributeInfo(this, a2, v9, *v13, v11);
      if ( v8 < 0 )
        goto LABEL_42;
      *(_QWORD *)(*((_QWORD *)this + 2) + 16LL * (unsigned int)i + 8) = *v13;
      v14 = *v11;
      if ( *v11 == 2 )
      {
        *((_QWORD *)this + 1) = *v13;
      }
      else
      {
        switch ( v14 )
        {
          case 80:
            *((_QWORD *)this + 6) = v11;
            break;
          case 1:
            *((_QWORD *)this + 8) = v11;
            break;
          case 33:
            *((_DWORD *)this + 43) = 1;
            break;
        }
      }
      v11 += (unsigned __int8)v11[1];
    }
    v8 = CPacketRadius::FillClientIPInfo(this, *(struct _IASATTRIBUTE **)&v6[8 * *((unsigned int *)this + 22)]);
    if ( v8 >= 0 )
    {
      *(_QWORD *)(*((_QWORD *)this + 2) + 16LL * *((unsigned int *)this + 22) + 8) = *(_QWORD *)&v6[8 * *((unsigned int *)this + 22)];
      v15 = *(_DWORD **)&v6[8 * (*((_DWORD *)this + 22) + 1)];
      v15[2] = 4117;
      v15[4] = 2;
      v15[6] = *(unsigned __int16 *)(*((_QWORD *)this + 10) + 2LL);
      v15[1] = 16;
      *(_QWORD *)(*((_QWORD *)this + 2) + 16LL * (unsigned int)(*((_DWORD *)this + 22) + 1) + 8) = *(_QWORD *)&v6[8 * (*((_DWORD *)this + 22) + 1)];
      v8 = CPacketRadius::FillPacketHeaderInfo(this, *(struct _IASATTRIBUTE **)&v6[8 * (*((_DWORD *)this + 22) + 2)]);
      if ( v8 >= 0 )
      {
        *(_QWORD *)(*((_QWORD *)this + 2) + 16LL * (unsigned int)(*((_DWORD *)this + 22) + 2) + 8) = *(_QWORD *)&v6[8 * (*((_DWORD *)this + 22) + 2)];
        v8 = CPacketRadius::FillSharedSecretInfo(this, *(struct _IASATTRIBUTE **)&v6[8 * (*((_DWORD *)this + 22) + 3)]);
        if ( v8 >= 0 )
        {
          *(_QWORD *)(*((_QWORD *)this + 2) + 16LL * (unsigned int)(*((_DWORD *)this + 22) + 3) + 8) = *(_QWORD *)&v6[8 * (*((_DWORD *)this + 22) + 3)];
          v16 = *(_DWORD **)&v6[8 * (*((_DWORD *)this + 22) + 4)];
          v16[2] = 4116;
          v16[4] = 2;
          v16[1] = 16;
          v16[6] = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 48LL))(*((_QWORD *)this + 16));
          *(_QWORD *)(*((_QWORD *)this + 2) + 16LL * (unsigned int)(*((_DWORD *)this + 22) + 4) + 8) = *(_QWORD *)&v6[8 * (*((_DWORD *)this + 22) + 4)];
          v8 = CPacketRadius::FillClientName(this, *(struct _IASATTRIBUTE **)&v6[8 * (*((_DWORD *)this + 22) + 5)]);
          if ( v8 >= 0 )
          {
            *(_QWORD *)(*((_QWORD *)this + 2) + 16LL * (unsigned int)(*((_DWORD *)this + 22) + 5) + 8) = *(_QWORD *)&v6[8 * (*((_DWORD *)this + 22) + 5)];
            v8 = CPacketRadius::FillServerIPInfo(this, *(struct _IASATTRIBUTE **)&v6[8 * (*((_DWORD *)this + 22) + 6)]);
            if ( v8 >= 0 )
            {
              *(_QWORD *)(*((_QWORD *)this + 2) + 16LL * (unsigned int)(*((_DWORD *)this + 22) + 6) + 8) = *(_QWORD *)&v6[8 * (*((_DWORD *)this + 22) + 6)];
              v17 = *(_DWORD **)&v6[8 * (*((_DWORD *)this + 22) + 7)];
              v17[2] = 8171;
              v17[4] = 1;
              v17[6] = *((_DWORD *)this + 42);
              *(_QWORD *)(*((_QWORD *)this + 2) + 16LL * (unsigned int)(*((_DWORD *)this + 22) + 7) + 8) = *(_QWORD *)&v6[8 * (*((_DWORD *)this + 22) + 7)];
              goto LABEL_46;
            }
          }
        }
      }
    }
LABEL_42:
    for ( j = 0; (unsigned int)j < (unsigned int)v4; j = (unsigned int)(j + 1) )
      IASAttributeRelease(*(LPVOID *)&v6[8 * j]);
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Unable to allocate IAS attribute while creating attribute collection");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_680dfa5530f83761685653fb6ea5f689_Traceguids, "NPSRAD");
  }
  v10 = v8 < 0;
  if ( v8 > 0 )
  {
    v8 = (unsigned __int16)v8 | 0x80070000;
    v10 = v8 < 0;
  }
  if ( v10 )
  {
LABEL_44:
    v19 = (void *)*((_QWORD *)this + 2);
    if ( v19 )
    {
      CoTaskMemFree(v19);
      *((_QWORD *)this + 2) = 0;
    }
  }
LABEL_46:
  if ( v6 && (unsigned int)v4 > 0x40 )
    CoTaskMemFree(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180012c68  push    rbx
0x180012c6a  push    rbp
0x180012c6b  push    rsi
0x180012c6c  push    rdi
0x180012c6d  push    r12
0x180012c6f  push    r13
0x180012c71  push    r14
0x180012c73  push    r15
0x180012c75  sub     rsp, 258h
0x180012c7c  mov     rax, cs:__security_cookie
0x180012c83  xor     rax, rsp
0x180012c86  mov     [rsp+298h+var_58], rax
0x180012c8e  mov     [rsp+298h+var_268], rdx
0x180012c93  mov     rdi, rcx
0x180012c96  xor     edx, edx; Val
0x180012c98  lea     rcx, [rsp+298h+var_258]; void *
0x180012c9d  mov     r8d, 200h; Size
0x180012ca3  call    memset_0
0x180012ca8  mov     ebp, [rdi+58h]
0x180012cab  mov     r14, [rdi+18h]
0x180012caf  add     ebp, 8
0x180012cb2  mov     ecx, ebp
0x180012cb4  shl     rcx, 4; cb
0x180012cb8  call    cs:__imp_CoTaskMemAlloc
0x180012cbe  mov     [rdi+10h], rax
0x180012cc2  test    rax, rax
0x180012cc5  jnz     short loc_180012D22
0x180012cc7  xor     esi, esi
0x180012cc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cd0  lea     rax, WPP_GLOBAL_Control
0x180012cd7  cmp     rcx, rax
0x180012cda  jz      short loc_180012D18
0x180012cdc  cmp     byte ptr [rcx+19h], 2
0x180012ce0  jb      short loc_180012D18
0x180012ce2  test    dword ptr [rcx+1Ch], 100h
0x180012ce9  jz      short loc_180012D18
0x180012ceb  lea     rcx, aUnableToAlloca_7; "Unable to allocate memory for Attribute"...
0x180012cf2  call    WppDbgPrint
0x180012cf7  lea     edx, [rsi+0Ch]
0x180012cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d01  lea     r9, aNpsrad; "NPSRAD"
0x180012d08  lea     r8, WPP_680dfa5530f83761685653fb6ea5f689_Traceguids
0x180012d0f  mov     rcx, [rcx+10h]
0x180012d13  call    WPP_SF_s
0x180012d18  mov     ebx, 8007000Eh
0x180012d1d  jmp     loc_18001304B
0x180012d22  cmp     ebp, 40h ; '@'
0x180012d25  jbe     short loc_180012D70
0x180012d27  lea     rcx, ds:0[rbp*8]; cb
0x180012d2f  call    cs:__imp_CoTaskMemAlloc
0x180012d35  mov     rsi, rax
0x180012d38  test    rax, rax
0x180012d3b  jnz     short loc_180012D75
0x180012d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d44  lea     rax, WPP_GLOBAL_Control
0x180012d4b  cmp     rcx, rax
0x180012d4e  jz      short loc_180012D18
0x180012d50  cmp     byte ptr [rcx+19h], 2
0x180012d54  jb      short loc_180012D18
0x180012d56  test    dword ptr [rcx+1Ch], 100h
0x180012d5d  jz      short loc_180012D18
0x180012d5f  lea     rcx, aUnableToAlloca_8; "Unable to allocate memory for Attribute"...
0x180012d66  call    WppDbgPrint
0x180012d6b  lea     edx, [rsi+0Dh]
0x180012d6e  jmp     short loc_180012CFA
0x180012d70  lea     rsi, [rsp+298h+var_258]
0x180012d75  mov     rdx, rsi
0x180012d78  mov     ecx, ebp
0x180012d7a  call    IASAttributeAlloc
0x180012d7f  mov     ebx, eax
0x180012d81  test    eax, eax
0x180012d83  jz      short loc_180012DF0
0x180012d85  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d8c  lea     rax, WPP_GLOBAL_Control
0x180012d93  cmp     rcx, rax
0x180012d96  jz      short loc_180012DD6
0x180012d98  cmp     byte ptr [rcx+19h], 2
0x180012d9c  jb      short loc_180012DD6
0x180012d9e  test    dword ptr [rcx+1Ch], 100h
0x180012da5  jz      short loc_180012DD6
0x180012da7  lea     rcx, aUnableToAlloca_2; "Unable to allocate IAS attribute while "...
0x180012dae  call    WppDbgPrint
0x180012db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180012dba  lea     r9, aNpsrad; "NPSRAD"
0x180012dc1  mov     edx, 0Eh
0x180012dc6  lea     r8, WPP_680dfa5530f83761685653fb6ea5f689_Traceguids
0x180012dcd  mov     rcx, [rcx+10h]
0x180012dd1  call    WPP_SF_s
0x180012dd6  test    ebx, ebx
0x180012dd8  jle     short loc_180012DE5
0x180012dda  movzx   ebx, bx
0x180012ddd  or      ebx, 80070000h
0x180012de3  test    ebx, ebx
0x180012de5  js      loc_18001304B
0x180012deb  jmp     loc_180013062
0x180012df0  add     r14, 14h
0x180012df4  xor     r15d, r15d
0x180012df7  mov     rcx, rdi; this
0x180012dfa  cmp     r15d, [rdi+58h]
0x180012dfe  jnb     short loc_180012E74
0x180012e00  mov     rdx, [rsp+298h+var_268]
0x180012e05  lea     r13, [rsi+r15*8]
0x180012e09  mov     r9, [r13+0]
0x180012e0d  mov     r12d, r15d
0x180012e10  mov     [rsp+298h+var_278], r14
0x180012e15  call    ?FillInAttributeInfo@CPacketRadius@@AEAAJPEAVCDictionary@@W4_packettype_@@PEAU_IASATTRIBUTE@@PEAU_attribute_@@@Z; CPacketRadius::FillInAttributeInfo(CDictionary *,_packettype_,_IASATTRIBUTE *,_attribute_ *)
0x180012e1a  mov     ebx, eax
0x180012e1c  test    eax, eax
0x180012e1e  js      loc_180013033
0x180012e24  mov     rax, [r13+0]
0x180012e28  add     r12, r12
0x180012e2b  mov     rcx, [rdi+10h]
0x180012e2f  mov     [rcx+r12*8+8], rax
0x180012e34  mov     al, [r14]
0x180012e37  cmp     al, 2
0x180012e39  jnz     short loc_180012E45
0x180012e3b  mov     rax, [r13+0]
0x180012e3f  mov     [rdi+8], rax
0x180012e43  jmp     short loc_180012E67
0x180012e45  cmp     al, 50h ; 'P'
0x180012e47  jnz     short loc_180012E4F
0x180012e49  mov     [rdi+30h], r14
0x180012e4d  jmp     short loc_180012E67
0x180012e4f  cmp     al, 1
0x180012e51  jnz     short loc_180012E59
0x180012e53  mov     [rdi+40h], r14
0x180012e57  jmp     short loc_180012E67
0x180012e59  cmp     al, 21h ; '!'
0x180012e5b  jnz     short loc_180012E67
0x180012e5d  mov     dword ptr [rdi+0ACh], 1
0x180012e67  movzx   eax, byte ptr [r14+1]
0x180012e6c  add     r14, rax
0x180012e6f  inc     r15d
0x180012e72  jmp     short loc_180012DF7
0x180012e74  mov     edx, [rdi+58h]
0x180012e77  mov     rdx, [rsi+rdx*8]; struct _IASATTRIBUTE *
0x180012e7b  call    ?FillClientIPInfo@CPacketRadius@@AEAAJPEAU_IASATTRIBUTE@@@Z; CPacketRadius::FillClientIPInfo(_IASATTRIBUTE *)
0x180012e80  mov     ebx, eax
0x180012e82  test    eax, eax
0x180012e84  js      loc_180013033
0x180012e8a  mov     eax, [rdi+58h]
0x180012e8d  mov     r14d, 10h
0x180012e93  mov     rcx, [rdi+10h]
0x180012e97  mov     edx, eax
0x180012e99  add     rdx, rdx
0x180012e9c  mov     rax, [rsi+rax*8]
0x180012ea0  mov     [rcx+rdx*8+8], rax
0x180012ea5  mov     eax, [rdi+58h]
0x180012ea8  inc     eax
0x180012eaa  mov     rdx, [rsi+rax*8]
0x180012eae  mov     dword ptr [rdx+8], 1015h
0x180012eb5  mov     dword ptr [rdx+10h], 2
0x180012ebc  mov     rax, [rdi+50h]
0x180012ec0  movzx   ecx, word ptr [rax+2]
0x180012ec4  mov     [rdx+18h], ecx
0x180012ec7  mov     [rdx+4], r14d
0x180012ecb  mov     eax, [rdi+58h]
0x180012ece  mov     rcx, [rdi+10h]
0x180012ed2  inc     eax
0x180012ed4  mov     edx, eax
0x180012ed6  add     rdx, rdx
0x180012ed9  mov     rax, [rsi+rax*8]
0x180012edd  mov     [rcx+rdx*8+8], rax
0x180012ee2  mov     rcx, rdi; this
0x180012ee5  mov     eax, [rdi+58h]
0x180012ee8  add     eax, 2
0x180012eeb  mov     rdx, [rsi+rax*8]; struct _IASATTRIBUTE *
0x180012eef  call    ?FillPacketHeaderInfo@CPacketRadius@@AEAAJPEAU_IASATTRIBUTE@@@Z; CPacketRadius::FillPacketHeaderInfo(_IASATTRIBUTE *)
0x180012ef4  mov     ebx, eax
0x180012ef6  test    eax, eax
0x180012ef8  js      loc_180013033
0x180012efe  mov     eax, [rdi+58h]
0x180012f01  mov     rcx, [rdi+10h]
0x180012f05  add     eax, 2
0x180012f08  mov     edx, eax
0x180012f0a  add     rdx, rdx
0x180012f0d  mov     rax, [rsi+rax*8]
0x180012f11  mov     [rcx+rdx*8+8], rax
0x180012f16  mov     rcx, rdi; this
0x180012f19  mov     eax, [rdi+58h]
0x180012f1c  add     eax, 3
0x180012f1f  mov     rdx, [rsi+rax*8]; struct _IASATTRIBUTE *
0x180012f23  call    ?FillSharedSecretInfo@CPacketRadius@@AEAAJPEAU_IASATTRIBUTE@@@Z; CPacketRadius::FillSharedSecretInfo(_IASATTRIBUTE *)
0x180012f28  mov     ebx, eax
0x180012f2a  test    eax, eax
0x180012f2c  js      loc_180013033
0x180012f32  mov     eax, [rdi+58h]
0x180012f35  mov     rcx, [rdi+10h]
0x180012f39  add     eax, 3
0x180012f3c  mov     edx, eax
0x180012f3e  add     rdx, rdx
0x180012f41  mov     rax, [rsi+rax*8]
0x180012f45  mov     [rcx+rdx*8+8], rax
0x180012f4a  mov     eax, [rdi+58h]
0x180012f4d  add     eax, 4
0x180012f50  mov     rbx, [rsi+rax*8]
0x180012f54  mov     dword ptr [rbx+8], 1014h
0x180012f5b  mov     dword ptr [rbx+10h], 2
0x180012f62  mov     [rbx+4], r14d
0x180012f66  mov     rcx, [rdi+80h]
0x180012f6d  mov     rax, [rcx]
0x180012f70  mov     rax, [rax+30h]
0x180012f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f79  mov     [rbx+18h], eax
0x180012f7c  mov     eax, [rdi+58h]
0x180012f7f  mov     rcx, [rdi+10h]
0x180012f83  add     eax, 4
0x180012f86  mov     edx, eax
0x180012f88  add     rdx, rdx
0x180012f8b  mov     rax, [rsi+rax*8]
0x180012f8f  mov     [rcx+rdx*8+8], rax
0x180012f94  mov     rcx, rdi; this
0x180012f97  mov     eax, [rdi+58h]
0x180012f9a  add     eax, 5
0x180012f9d  mov     rdx, [rsi+rax*8]; struct _IASATTRIBUTE *
0x180012fa1  call    ?FillClientName@CPacketRadius@@AEAAJPEAU_IASATTRIBUTE@@@Z; CPacketRadius::FillClientName(_IASATTRIBUTE *)
0x180012fa6  mov     ebx, eax
0x180012fa8  test    eax, eax
0x180012faa  js      loc_180013033
0x180012fb0  mov     eax, [rdi+58h]
0x180012fb3  mov     rcx, [rdi+10h]
0x180012fb7  add     eax, 5
0x180012fba  mov     edx, eax
0x180012fbc  add     rdx, rdx
0x180012fbf  mov     rax, [rsi+rax*8]
0x180012fc3  mov     [rcx+rdx*8+8], rax
0x180012fc8  mov     rcx, rdi; this
0x180012fcb  mov     eax, [rdi+58h]
0x180012fce  add     eax, 6
0x180012fd1  mov     rdx, [rsi+rax*8]; struct _IASATTRIBUTE *
0x180012fd5  call    ?FillServerIPInfo@CPacketRadius@@AEAAJPEAU_IASATTRIBUTE@@@Z; CPacketRadius::FillServerIPInfo(_IASATTRIBUTE *)
0x180012fda  mov     ebx, eax
0x180012fdc  test    eax, eax
0x180012fde  js      short loc_180013033
0x180012fe0  mov     eax, [rdi+58h]
0x180012fe3  mov     rcx, [rdi+10h]
0x180012fe7  add     eax, 6
0x180012fea  mov     edx, eax
0x180012fec  add     rdx, rdx
0x180012fef  mov     rax, [rsi+rax*8]
0x180012ff3  mov     [rcx+rdx*8+8], rax
0x180012ff8  mov     eax, [rdi+58h]
0x180012ffb  add     eax, 7
0x180012ffe  mov     rcx, [rsi+rax*8]
0x180013002  mov     dword ptr [rcx+8], 1FEBh
0x180013009  mov     dword ptr [rcx+10h], 1
0x180013010  mov     eax, [rdi+0A8h]
0x180013016  mov     [rcx+18h], eax
0x180013019  mov     eax, [rdi+58h]
0x18001301c  mov     rcx, [rdi+10h]
0x180013020  add     eax, 7
0x180013023  mov     edx, eax
0x180013025  add     rdx, rdx
0x180013028  mov     rax, [rsi+rax*8]
0x18001302c  mov     [rcx+rdx*8+8], rax
0x180013031  jmp     short loc_180013062
0x180013033  xor     r14d, r14d
0x180013036  test    ebp, ebp
0x180013038  jz      short loc_18001304B
0x18001303a  mov     rcx, [rsi+r14*8]; pv
0x18001303e  call    IASAttributeRelease
0x180013043  inc     r14d
0x180013046  cmp     r14d, ebp
0x180013049  jb      short loc_18001303A
0x18001304b  mov     rcx, [rdi+10h]; pv
0x18001304f  test    rcx, rcx
0x180013052  jz      short loc_180013062
0x180013054  call    cs:__imp_CoTaskMemFree
0x18001305a  mov     qword ptr [rdi+10h], 0
0x180013062  test    rsi, rsi
0x180013065  jz      short loc_180013075
0x180013067  cmp     ebp, 40h ; '@'
0x18001306a  jbe     short loc_180013075
0x18001306c  mov     rcx, rsi; pv
0x18001306f  call    cs:__imp_CoTaskMemFree
0x180013075  mov     eax, ebx
0x180013077  mov     rcx, [rsp+298h+var_58]
0x18001307f  xor     rcx, rsp; StackCookie
0x180013082  call    __security_check_cookie
0x180013087  add     rsp, 258h
0x18001308e  pop     r15
0x180013090  pop     r14
0x180013092  pop     r13
0x180013094  pop     r12
0x180013096  pop     rdi
0x180013097  pop     rsi
0x180013098  pop     rbp
0x180013099  pop     rbx
0x18001309a  retn
```
