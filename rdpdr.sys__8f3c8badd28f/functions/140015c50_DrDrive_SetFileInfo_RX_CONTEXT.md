# DrDrive::SetFileInfo(_RX_CONTEXT *)

- ea: `0x140015c50`
- end: `0x140016123`
- name: `?SetFileInfo@DrDrive@@UEAAJPEAU_RX_CONTEXT@@@Z`
- size: `1235`
- prototype: `__int64 __fastcall(DrDrive *__hidden this, struct _RX_CONTEXT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callees

- `0x1400016a0`
- `0x140001890`
- `0x140001e30`
- `0x140003188`
- `0x14000324c`
- `0x14000327c`
- `0x1400032c0`
- `0x140006560`
- `0x1400065c0`
- `0x1400068c0`
- `0x140015c50`

## pseudocode

```c
__int64 __fastcall DrDrive::SetFileInfo(DrDrive *this, struct _RX_CONTEXT *a2)
{
  RefCount *v2; // rax
  RefCount *v5; // rbx
  __int64 v7; // r9
  unsigned int v8; // ebx
  ULONG Flags; // r15d
  char v10; // r14
  unsigned int v11; // ebp
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // ecx
  __int64 v15; // r9
  _DWORD *v16; // rax
  _DWORD *v17; // rsi
  void *v18; // rcx
  size_t v19; // r8
  PDFS_NAME_CONTEXT v20; // rdx
  PDFS_NAME_CONTEXT v21; // rdx
  PDFS_NAME_CONTEXT DfsNameContext; // rcx
  RefCount *v23; // [rsp+80h] [rbp+8h] BYREF
  RefCount *v24; // [rsp+88h] [rbp+10h] BYREF

  v2 = (RefCount *)*((_QWORD *)this + 4);
  v24 = v2;
  if ( v2 )
    RefCount::AddRef(v2);
  v5 = *(RefCount **)&a2->pFobx->OffsetOfNextEaToReturn;
  v23 = v5;
  if ( v5 )
    RefCount::AddRef(v5);
  if ( *((_DWORD *)v2 + 149) != 3 )
  {
    a2->InformationToReturn = 0;
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v23);
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v24);
    return 3221225629LL;
  }
  if ( !v5 )
    goto LABEL_12;
  v7 = *((unsigned int *)this + 14);
  if ( (_DWORD)v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, v7);
LABEL_12:
    v8 = -1073741667;
LABEL_13:
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v23);
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v24);
    return v8;
  }
  if ( !*((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) )
  {
    a2->InformationToReturn = 0;
LABEL_16:
    v8 = 0;
    goto LABEL_13;
  }
  Flags = a2->LowIoContext.ParamsFor.Locks.Flags;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, Flags);
  switch ( Flags )
  {
    case 4u:
      if ( *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) != 40 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          break;
        v13 = 67;
        goto LABEL_82;
      }
      v10 = 1;
      v11 = 92;
      goto LABEL_68;
    case 0xAu:
      v14 = *(_DWORD *)(a2->LowIoContext.ParamsFor.ReadWrite.ByteOffset + 16);
      if ( v14 + 20 >= v14 )
      {
        v15 = *((unsigned int *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8);
        if ( (_DWORD)v15 != v14 + 20 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, v15, v14);
          break;
        }
        if ( v14 + 6 >= v14 )
        {
          if ( (_DWORD)v15 == v14 + 6 )
          {
            v11 = v15 + 58;
            if ( (int)v15 + 58 >= (unsigned int)v15 )
            {
              v10 = 0;
              goto LABEL_60;
            }
          }
          else
          {
            v11 = v14 + 64;
            if ( v14 + 64 >= v14 )
            {
              v10 = 1;
LABEL_60:
              if ( !v11 )
                break;
LABEL_68:
              v16 = operator new(v11, 0x100u);
              v17 = v16;
              if ( !v16 )
              {
                v8 = -1073741670;
                goto LABEL_13;
              }
              memset(v16, 0, v11);
              *v17 = 1230128242;
              v17[1] = *((_DWORD *)this + 10);
              v17[2] = *((_DWORD *)v5 + 6);
              *((_QWORD *)v17 + 2) = 6;
              v17[6] = Flags;
              if ( v11 <= 0x38 )
                goto LABEL_77;
              if ( v10 )
              {
                if ( Flags == 4 )
                {
                  DfsNameContext = a2->Create.NtCreateParameters.DfsNameContext;
                  v17[7] = 36;
                  *((_QWORD *)v17 + 10) = *((_QWORD *)DfsNameContext + 3);
                  *((_QWORD *)v17 + 7) = *(_QWORD *)DfsNameContext;
                  v17[22] = *((_DWORD *)DfsNameContext + 8);
                  *((_QWORD *)v17 + 8) = *((_QWORD *)DfsNameContext + 1);
                  *((_QWORD *)v17 + 9) = *((_QWORD *)DfsNameContext + 2);
                  goto LABEL_77;
                }
                if ( Flags != 10 )
                {
LABEL_77:
                  v8 = (*(__int64 (__fastcall **)(DrDrive *, struct _RX_CONTEXT *, _DWORD *, _QWORD, bool, union _LARGE_INTEGER *, _DWORD))(*(_QWORD *)this + 24LL))(
                         this,
                         a2,
                         v17,
                         v11,
                         ((__int64)a2->RdbssDbgExtension & 0x1000) == 0,
                         &g_IOTimeOut,
                         0);
                  operator delete(v17);
                  goto LABEL_13;
                }
                v21 = a2->Create.NtCreateParameters.DfsNameContext;
                v17[7] = v11 - 56;
                v18 = (char *)v17 + 62;
                *((_BYTE *)v17 + 56) = *(_BYTE *)v21;
                *((_BYTE *)v17 + 57) = 0;
                *(_DWORD *)((char *)v17 + 58) = *((_DWORD *)v21 + 4) + 2;
                v19 = *((unsigned int *)v21 + 4);
                v20 = (PDFS_NAME_CONTEXT)((char *)v21 + 20);
              }
              else
              {
                v18 = v17 + 14;
                v17[7] = *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8);
                v19 = *((unsigned int *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8);
                v20 = a2->Create.NtCreateParameters.DfsNameContext;
              }
              memmove(v18, v20, v19);
              goto LABEL_77;
            }
          }
        }
      }
      v8 = -2147483643;
      goto LABEL_13;
    case 0xBu:
      goto LABEL_48;
    case 0xDu:
      if ( *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) != 1 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          break;
        v13 = 69;
        goto LABEL_82;
      }
      if ( !*(_BYTE *)a2->Create.NtCreateParameters.DfsNameContext )
        goto LABEL_16;
      v10 = 0;
      v11 = 56;
      goto LABEL_68;
    case 0x13u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
      if ( *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) == 8 )
      {
LABEL_31:
        v10 = 0;
        v11 = 64;
        goto LABEL_68;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v13 = 72;
        goto LABEL_82;
      }
      break;
    case 0x14u:
      if ( *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) == 8 )
        goto LABEL_31;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v13 = 68;
LABEL_82:
        WPP_SF_(v12->AttachedDevice, v13, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
      }
      break;
    case 0x23u:
LABEL_48:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, Flags);
      v8 = -1073741822;
      goto LABEL_13;
    default:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, Flags);
      break;
  }
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v23);
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v24);
  return 3221225485LL;
}

```

## disassembly

```asm
0x140015c50  mov     r11, rsp
0x140015c53  mov     [r11+18h], rbx
0x140015c57  push    rbp
0x140015c58  push    rsi
0x140015c59  push    rdi
0x140015c5a  push    r12
0x140015c5c  push    r13
0x140015c5e  push    r14
0x140015c60  push    r15
0x140015c62  sub     rsp, 40h
0x140015c66  mov     rax, [rcx+20h]
0x140015c6a  xor     r12d, r12d
0x140015c6d  mov     [r11+10h], rax
0x140015c71  mov     rdi, rdx
0x140015c74  mov     r13, rcx
0x140015c77  test    rax, rax
0x140015c7a  jz      short loc_140015C84
0x140015c7c  mov     rcx, rax; this
0x140015c7f  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140015c84  mov     rbx, [rdx+40h]
0x140015c88  mov     rbx, [rbx+40h]
0x140015c8c  mov     [rsp+78h+arg_0], rbx
0x140015c94  test    rbx, rbx
0x140015c97  jz      short loc_140015CA1
0x140015c99  mov     rcx, rbx; this
0x140015c9c  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140015ca1  cmp     dword ptr [rax+254h], 3
0x140015ca8  jz      short loc_140015CD2
0x140015caa  lea     rcx, [rsp+78h+arg_0]
0x140015cb2  mov     [rdx+0B8h], r12
0x140015cb9  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140015cbe  lea     rcx, [rsp+78h+arg_8]
0x140015cc6  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140015ccb  mov     eax, 0C000009Dh
0x140015cd0  jmp     short loc_140015D2F
0x140015cd2  test    rbx, rbx
0x140015cd5  jz      short loc_140015D0E
0x140015cd7  mov     r9d, [r13+38h]
0x140015cdb  test    r9d, r9d
0x140015cde  jz      short loc_140015D48
0x140015ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x140015ce7  lea     rsi, WPP_GLOBAL_Control
0x140015cee  cmp     rcx, rsi
0x140015cf1  jz      short loc_140015D0E
0x140015cf3  cmp     byte ptr [rcx+29h], 5
0x140015cf7  jb      short loc_140015D0E
0x140015cf9  mov     rcx, [rcx+18h]
0x140015cfd  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140015d04  mov     edx, 41h ; 'A'
0x140015d09  call    WPP_SF_d
0x140015d0e  mov     ebx, 0C000009Dh
0x140015d13  lea     rcx, [rsp+78h+arg_0]
0x140015d1b  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140015d20  lea     rcx, [rsp+78h+arg_8]
0x140015d28  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140015d2d  mov     eax, ebx
0x140015d2f  mov     rbx, [rsp+78h+arg_10]
0x140015d37  add     rsp, 40h
0x140015d3b  pop     r15
0x140015d3d  pop     r14
0x140015d3f  pop     r13
0x140015d41  pop     r12
0x140015d43  pop     rdi
0x140015d44  pop     rsi
0x140015d45  pop     rbp
0x140015d46  retn
0x140015d48  cmp     [rdx+1D8h], r12d
0x140015d4f  jnz     short loc_140015D5D
0x140015d51  mov     [rdx+0B8h], r12
0x140015d58  mov     ebx, r12d
0x140015d5b  jmp     short loc_140015D13
0x140015d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d64  lea     rsi, WPP_GLOBAL_Control
0x140015d6b  mov     r15d, [rdx+1C0h]
0x140015d72  lea     rbp, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140015d79  cmp     rcx, rsi
0x140015d7c  jz      short loc_140015D98
0x140015d7e  cmp     byte ptr [rcx+29h], 5
0x140015d82  jb      short loc_140015D98
0x140015d84  mov     rcx, [rcx+18h]
0x140015d88  mov     edx, 42h ; 'B'
0x140015d8d  mov     r9d, r15d
0x140015d90  mov     r8, rbp
0x140015d93  call    WPP_SF_d
0x140015d98  mov     ecx, r15d
0x140015d9b  sub     ecx, 4
0x140015d9e  jz      loc_140015F92
0x140015da4  sub     ecx, 6
0x140015da7  jz      loc_140015F09
0x140015dad  sub     ecx, 1
0x140015db0  jz      loc_140015ED9
0x140015db6  sub     ecx, 2
0x140015db9  jz      loc_140015E8F
0x140015dbf  sub     ecx, 6
0x140015dc2  jz      short loc_140015E3F
0x140015dc4  sub     ecx, 1
0x140015dc7  jz      short loc_140015E05
0x140015dc9  cmp     ecx, 0Fh
0x140015dcc  jz      loc_140015ED9
0x140015dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140015dd9  cmp     rcx, rsi
0x140015ddc  jz      loc_1400160FF
0x140015de2  cmp     byte ptr [rcx+29h], 5
0x140015de6  jb      loc_1400160FF
0x140015dec  mov     rcx, [rcx+18h]
0x140015df0  mov     edx, 4Ah ; 'J'
0x140015df5  mov     r9d, r15d
0x140015df8  mov     r8, rbp
0x140015dfb  call    WPP_SF_d
0x140015e00  jmp     loc_1400160FF
0x140015e05  cmp     dword ptr [rdi+1D8h], 8
0x140015e0c  jnz     short loc_140015E1B
0x140015e0e  mov     r14b, r12b
0x140015e11  mov     ebp, 40h ; '@'
0x140015e16  jmp     loc_140015FA7
0x140015e1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015e22  cmp     rcx, rsi
0x140015e25  jz      loc_1400160FF
0x140015e2b  cmp     byte ptr [rcx+29h], 2
0x140015e2f  jb      loc_1400160FF
0x140015e35  mov     edx, 44h ; 'D'
0x140015e3a  jmp     loc_1400160F3
0x140015e3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140015e46  cmp     rcx, rsi
0x140015e49  jz      short loc_140015E62
0x140015e4b  cmp     byte ptr [rcx+29h], 4
0x140015e4f  jb      short loc_140015E62
0x140015e51  mov     rcx, [rcx+18h]
0x140015e55  mov     edx, 47h ; 'G'
0x140015e5a  mov     r8, rbp
0x140015e5d  call    WPP_SF_
0x140015e62  cmp     dword ptr [rdi+1D8h], 8
0x140015e69  jz      short loc_140015E0E
0x140015e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015e72  cmp     rcx, rsi
0x140015e75  jz      loc_1400160FF
0x140015e7b  cmp     byte ptr [rcx+29h], 2
0x140015e7f  jb      loc_1400160FF
0x140015e85  mov     edx, 48h ; 'H'
0x140015e8a  jmp     loc_1400160F3
0x140015e8f  cmp     dword ptr [rdi+1D8h], 1
0x140015e96  jnz     short loc_140015EB5
0x140015e98  mov     rax, [rdi+1C8h]
0x140015e9f  cmp     [rax], r12b
0x140015ea2  jz      loc_140015D58
0x140015ea8  mov     r14b, r12b
0x140015eab  mov     ebp, 38h ; '8'
0x140015eb0  jmp     loc_140015FA7
0x140015eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140015ebc  cmp     rcx, rsi
0x140015ebf  jz      loc_1400160FF
0x140015ec5  cmp     byte ptr [rcx+29h], 2
0x140015ec9  jb      loc_1400160FF
0x140015ecf  mov     edx, 45h ; 'E'
0x140015ed4  jmp     loc_1400160F3
0x140015ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x140015ee0  cmp     rcx, rsi
0x140015ee3  jz      short loc_140015EFF
0x140015ee5  cmp     byte ptr [rcx+29h], 5
0x140015ee9  jb      short loc_140015EFF
0x140015eeb  mov     rcx, [rcx+18h]
0x140015eef  mov     edx, 49h ; 'I'
0x140015ef4  mov     r9d, r15d
0x140015ef7  mov     r8, rbp
0x140015efa  call    WPP_SF_d
0x140015eff  mov     ebx, 0C0000002h
0x140015f04  jmp     loc_140015D13
0x140015f09  mov     rax, [rdi+1C8h]
0x140015f10  mov     ecx, [rax+10h]
0x140015f13  lea     eax, [rcx+14h]
0x140015f16  cmp     eax, ecx
0x140015f18  jb      short loc_140015F88
0x140015f1a  mov     r9d, [rdi+1D8h]
0x140015f21  cmp     r9d, eax
0x140015f24  jnz     short loc_140015F54
0x140015f26  lea     eax, [rcx+6]
0x140015f29  cmp     eax, ecx
0x140015f2b  jb      short loc_140015F88
0x140015f2d  cmp     r9d, eax
0x140015f30  jnz     short loc_140015F40
0x140015f32  lea     ebp, [r9+3Ah]
0x140015f36  cmp     ebp, r9d
0x140015f39  jb      short loc_140015F88
0x140015f3b  mov     r14b, r12b
0x140015f3e  jmp     short loc_140015F4A
0x140015f40  lea     ebp, [rcx+40h]
0x140015f43  cmp     ebp, ecx
0x140015f45  jb      short loc_140015F88
0x140015f47  mov     r14b, 1
0x140015f4a  test    ebp, ebp
0x140015f4c  jz      loc_1400160FF
0x140015f52  jmp     short loc_140015FA7
0x140015f54  mov     rax, cs:WPP_GLOBAL_Control
0x140015f5b  cmp     rax, rsi
0x140015f5e  jz      loc_1400160FF
0x140015f64  cmp     byte ptr [rax+29h], 2
0x140015f68  jb      loc_1400160FF
0x140015f6e  mov     [rsp+78h+var_58], ecx
0x140015f72  mov     edx, 46h ; 'F'
0x140015f77  mov     rcx, [rax+18h]
0x140015f7b  mov     r8, rbp
0x140015f7e  call    WPP_SF_dd
0x140015f83  jmp     loc_1400160FF
0x140015f88  mov     ebx, 80000005h
0x140015f8d  jmp     loc_140015D13
0x140015f92  cmp     dword ptr [rdi+1D8h], 28h ; '('
0x140015f99  jnz     loc_1400160DC
0x140015f9f  mov     r14b, 1
0x140015fa2  mov     ebp, 5Ch ; '\'
0x140015fa7  mov     edx, 100h; unsigned __int64
0x140015fac  mov     ecx, ebp; unsigned __int64
0x140015fae  mov     r12d, ebp
0x140015fb1  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x140015fb6  mov     rsi, rax
0x140015fb9  test    rax, rax
0x140015fbc  jz      loc_1400160D2
0x140015fc2  mov     r8d, r12d; Size
0x140015fc5  xor     edx, edx; Val
0x140015fc7  mov     rcx, rax; void *
0x140015fca  call    memset
0x140015fcf  mov     dword ptr [rsi], 49524472h
0x140015fd5  mov     eax, [r13+28h]
0x140015fd9  mov     [rsi+4], eax
0x140015fdc  mov     eax, [rbx+18h]
0x140015fdf  xor     ebx, ebx
0x140015fe1  mov     [rsi+8], eax
0x140015fe4  mov     qword ptr [rsi+10h], 6
0x140015fec  mov     [rsi+18h], r15d
0x140015ff0  cmp     ebp, 38h ; '8'
0x140015ff3  jbe     loc_14001608B
0x140015ff9  test    r14b, r14b
0x140015ffc  jnz     short loc_140016020
0x140015ffe  mov     eax, [rdi+1D8h]
0x140016004  lea     rcx, [rsi+38h]; void *
0x140016008  mov     [rsi+1Ch], eax
0x14001600b  mov     r8d, [rdi+1D8h]; Size
0x140016012  mov     rdx, [rdi+1C8h]; Src
0x140016019  call    memmove
0x14001601e  jmp     short loc_14001608B
0x140016020  cmp     r15d, 4
0x140016024  jz      short loc_140016058
0x140016026  cmp     r15d, 0Ah
0x14001602a  jnz     short loc_14001608B
0x14001602c  mov     rdx, [rdi+1C8h]
0x140016033  lea     eax, [rbp-38h]
0x140016036  mov     [rsi+1Ch], eax
0x140016039  lea     rcx, [rsi+3Eh]
0x14001603d  mov     al, [rdx]
0x14001603f  mov     [rsi+38h], al
0x140016042  mov     [rsi+39h], bl
0x140016045  mov     eax, [rdx+10h]
0x140016048  add     eax, 2
0x14001604b  mov     [rsi+3Ah], eax
0x14001604e  mov     r8d, [rdx+10h]
0x140016052  add     rdx, 14h
0x140016056  jmp     short loc_140016019
0x140016058  mov     rcx, [rdi+1C8h]
0x14001605f  mov     dword ptr [rsi+1Ch], 24h ; '$'
0x140016066  mov     rax, [rcx+18h]
0x14001606a  mov     [rsi+50h], rax
0x14001606e  mov     rax, [rcx]
0x140016071  mov     [rsi+38h], rax
0x140016075  mov     eax, [rcx+20h]
0x140016078  mov     [rsi+58h], eax
0x14001607b  mov     rax, [rcx+8]
0x14001607f  mov     [rsi+40h], rax
0x140016083  mov     rax, [rcx+10h]
0x140016087  mov     [rsi+48h], rax
0x14001608b  mov     ecx, [rdi+78h]
0x14001608e  lea     rdx, ?g_IOTimeOut@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_IOTimeOut
0x140016095  mov     rax, [r13+0]
0x140016099  mov     r9d, ebp
0x14001609c  shr     ecx, 0Ch
0x14001609f  mov     r8, rsi
0x1400160a2  not     cl
0x1400160a4  mov     [rsp+78h+var_48], ebx
0x1400160a8  and     cl, 1
0x1400160ab  mov     [rsp+78h+var_50], rdx
0x1400160b0  mov     rax, [rax+18h]
0x1400160b4  mov     rdx, rdi
0x1400160b7  mov     byte ptr [rsp+78h+var_58], cl
0x1400160bb  mov     rcx, r13
0x1400160be  call    _guard_dispatch_icall
0x1400160c3  mov     rcx, rsi; void *
0x1400160c6  mov     ebx, eax
0x1400160c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400160cd  jmp     loc_140015D13
0x1400160d2  mov     ebx, 0C000009Ah
0x1400160d7  jmp     loc_140015D13
0x1400160dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400160e3  cmp     rcx, rsi
0x1400160e6  jz      short loc_1400160FF
0x1400160e8  cmp     byte ptr [rcx+29h], 2
0x1400160ec  jb      short loc_1400160FF
0x1400160ee  mov     edx, 43h ; 'C'
0x1400160f3  mov     rcx, [rcx+18h]
0x1400160f7  mov     r8, rbp
0x1400160fa  call    WPP_SF_
0x1400160ff  lea     rcx, [rsp+78h+arg_0]
0x140016107  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
  ... truncated ...
```
