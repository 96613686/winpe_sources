# sub_1400DEEE0

- ea: `0x1400deee0`
- end: `0x1400df129`
- name: `sub_1400DEEE0`
- size: `585`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1400d9ed0`
- `0x1400dee20`

## callees

- `0x14004cf20`
- `0x14004f334`
- `0x14005d9e0`
- `0x140064ec0`
- `0x140064ed0`
- `0x1400aabd0`
- `0x1400affa0`
- `0x1400b0000`
- `0x1400deee0`
- `0x14011fa70`
- `0x1401cf2c0`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x1400defa3`
- `KERNEL32!CreateFileMappingW` at `0x1400defa3`
- `KERNEL32!MapViewOfFile` at `0x1400df001`
- `KERNEL32!MapViewOfFile` at `0x1400df001`

## pseudocode

```c
__int64 __fastcall sub_1400DEEE0(__int64 a1, __int64 *a2, int a3)
{
  unsigned __int64 v6; // rdi
  DWORD v7; // ebp
  DWORD v8; // ebx
  unsigned __int64 v9; // r12
  void *v10; // rax
  HANDLE FileMappingW; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r14
  __int64 v17; // r8
  __int128 v18; // rax
  char *v19; // rax
  __int64 v21; // rcx
  __int64 v22; // [rsp+0h] [rbp-E8h] BYREF
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-C8h]
  __int64 v24; // [rsp+30h] [rbp-B8h] BYREF
  int v25; // [rsp+3Ch] [rbp-ACh] BYREF
  _QWORD v26[4]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v27[72]; // [rsp+60h] [rbp-88h] BYREF
  __int64 v28; // [rsp+A8h] [rbp-40h]

  memset(v27, 0, 64);
  sub_14004CF20(v26, "MapFileRegionToMemory", "..\\..\\base\\files\\memory_mapped_file_win.cc", 72);
  LODWORD(v6) = 0;
  sub_1400AABD0(v27, v26, 0);
  if ( (unsigned __int8)sub_140064ED0(a1) )
  {
    if ( a3 )
    {
      switch ( a3 )
      {
        case 1:
          v7 = 4;
          v8 = 2;
          goto LABEL_4;
        case 2:
          v7 = 8;
          v8 = 1;
          goto LABEL_4;
        case 3:
          v6 = a2[1];
          v9 = HIDWORD(v6);
          v7 = 4;
          v8 = 2;
          goto LABEL_5;
        case 4:
          LODWORD(v6) = sub_1400B0000(a1);
          break;
        default:
          v8 = 0;
          v7 = 0;
          goto LABEL_4;
      }
    }
    else
    {
      v7 = 2;
      v8 = 4;
LABEL_4:
      LODWORD(v9) = 0;
LABEL_5:
      v10 = (void *)sub_140064EC0(a1);
      dwMaximumSizeLow[0] = v6;
      LODWORD(v6) = 0;
      FileMappingW = CreateFileMappingW(v10, 0, v7, v9, dwMaximumSizeLow[0], 0);
      sub_14004F334(a1 + 64, FileMappingW);
      v12 = *(_QWORD *)(a1 + 64);
      if ( v12 && (unsigned int)v12 <= 0xFFFFFFF3 )
      {
        v25 = 0;
        v13 = *a2;
        v14 = a2[1];
        if ( *(_OWORD *)a2 == 0 )
        {
          v15 = sub_1401CF2C0(a1);
          LODWORD(v6) = 0;
          if ( v15 <= 0 )
            goto LABEL_12;
          v16 = v15;
          LODWORD(v17) = 0;
          *(_QWORD *)&v18 = 0;
        }
        else
        {
          v26[0] = 0;
          v24 = 0;
          sub_1400AFFA0(v13, v14, (unsigned int)v26, (unsigned int)&v24, (__int64)&v25);
          v16 = a2[1];
          v18 = (unsigned __int64)v16 + (__int128)v25;
          v21 = -(__int64)(BYTE8(v18) & 1);
          BYTE8(v18) = v21 != *((_QWORD *)&v18 + 1);
          LODWORD(v6) = v26[0];
          if ( v26[0] < 0LL
            || BYTE8(v18)
            || ((((unsigned __int128)(unsigned __int64)v16 + v25) >> 64) & 1) == 1
            || !((unsigned __int64)v18 | v21 & 1) )
          {
            goto LABEL_23;
          }
          v17 = HIDWORD(v26[0]);
        }
        v19 = (char *)MapViewOfFile(*(HANDLE *)(a1 + 64), v8, v17, v6, v18);
        if ( !v19 )
          goto LABEL_23;
        *(_QWORD *)(a1 + 48) = &v19[v25];
        *(_QWORD *)(a1 + 56) = v16;
        LOBYTE(v6) = 1;
      }
    }
  }
LABEL_12:
  while ( 1 )
  {
    sub_14005D9E0(v27);
    if ( _security_cookie == ((unsigned __int64)&v22 ^ v28) )
      break;
LABEL_23:
    LODWORD(v6) = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400deee0  push    r15
0x1400deee2  push    r14
0x1400deee4  push    r12
0x1400deee6  push    rsi
0x1400deee7  push    rdi
0x1400deee8  push    rbp
0x1400deee9  push    rbx
0x1400deeea  sub     rsp, 0B0h
0x1400deef1  mov     ebx, r8d
0x1400deef4  mov     r14, rdx
0x1400deef7  mov     rsi, rcx
0x1400deefa  mov     rax, cs:__security_cookie
0x1400def01  xor     rax, rsp
0x1400def04  mov     [rsp+0E8h+var_40], rax
0x1400def0c  xorps   xmm0, xmm0
0x1400def0f  lea     r15, [rsp+0E8h+var_88]
0x1400def14  movaps  xmmword ptr [r15+30h], xmm0
0x1400def19  movaps  xmmword ptr [r15+20h], xmm0
0x1400def1e  movaps  xmmword ptr [r15+10h], xmm0
0x1400def23  movaps  xmmword ptr [r15], xmm0
0x1400def27  lea     rdx, aMapfileregiont; "MapFileRegionToMemory"
0x1400def2e  lea     r8, aBaseFilesMemor; "..\\..\\base\\files\\memory_mapped_file"...
0x1400def35  lea     r12, [rsp+0E8h+var_A8]
0x1400def3a  mov     rcx, r12
0x1400def3d  mov     r9d, 48h ; 'H'
0x1400def43  call    sub_14004CF20
0x1400def48  xor     edi, edi
0x1400def4a  mov     rcx, r15
0x1400def4d  mov     rdx, r12
0x1400def50  xor     r8d, r8d
0x1400def53  call    sub_1400AABD0
0x1400def58  mov     rcx, rsi
0x1400def5b  call    sub_140064ED0
0x1400def60  test    al, al
0x1400def62  jz      loc_1400DF023
0x1400def68  test    ebx, ebx
0x1400def6a  jnz     loc_1400DF05C
0x1400def70  mov     ebp, 2
0x1400def75  mov     ebx, 4
0x1400def7a  xor     r12d, r12d
0x1400def7d  lea     r15, [rsi+40h]
0x1400def81  mov     rcx, rsi
0x1400def84  call    sub_140064EC0
0x1400def89  mov     [rsp+0E8h+dwMaximumSizeLow], edi; dwMaximumSizeLow
0x1400def8d  mov     [rsp+0E8h+lpName], 0; lpName
0x1400def96  xor     edi, edi
0x1400def98  mov     rcx, rax; hFile
0x1400def9b  xor     edx, edx; lpFileMappingAttributes
0x1400def9d  mov     r8d, ebp; flProtect
0x1400defa0  mov     r9d, r12d; dwMaximumSizeHigh
0x1400defa3  call    cs:CreateFileMappingW
0x1400defa9  mov     rcx, r15
0x1400defac  mov     rdx, rax
0x1400defaf  call    sub_14004F334
0x1400defb4  mov     rax, [rsi+40h]
0x1400defb8  test    rax, rax
0x1400defbb  jz      short loc_1400DF023
0x1400defbd  cmp     eax, 0FFFFFFF3h
0x1400defc0  ja      short loc_1400DF023
0x1400defc2  mov     [rsp+0E8h+var_AC], 0
0x1400defca  mov     rcx, [r14]
0x1400defcd  mov     rdx, [r14+8]
0x1400defd1  mov     rax, rcx
0x1400defd4  or      rax, rdx
0x1400defd7  jnz     loc_1400DF0AC
0x1400defdd  mov     rcx, rsi
0x1400defe0  call    sub_1401CF2C0
0x1400defe5  xor     edi, edi
0x1400defe7  test    rax, rax
0x1400defea  jle     short loc_1400DF023
0x1400defec  mov     r14, rax
0x1400defef  xor     r8d, r8d; dwFileOffsetHigh
0x1400deff2  xor     eax, eax
0x1400deff4  mov     rcx, [r15]; hFileMappingObject
0x1400deff7  mov     qword ptr [rsp+0E8h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x1400deffc  mov     edx, ebx; dwDesiredAccess
0x1400deffe  mov     r9d, edi; dwFileOffsetLow
0x1400df001  call    cs:MapViewOfFile
0x1400df007  test    rax, rax
0x1400df00a  jz      loc_140170BB2
0x1400df010  movsxd  rcx, [rsp+0E8h+var_AC]
0x1400df015  add     rax, rcx
0x1400df018  mov     [rsi+30h], rax
0x1400df01c  mov     [rsi+38h], r14
0x1400df020  mov     dil, 1
0x1400df023  lea     rcx, [rsp+0E8h+var_88]
0x1400df028  call    sub_14005D9E0
0x1400df02d  mov     rax, [rsp+0E8h+var_40]
0x1400df035  xor     rax, rsp
0x1400df038  mov     rcx, cs:__security_cookie
0x1400df03f  cmp     rcx, rax
0x1400df042  jnz     loc_140170BA2
0x1400df048  mov     eax, edi
0x1400df04a  add     rsp, 0B0h
0x1400df051  pop     rbx
0x1400df052  pop     rbp
0x1400df053  pop     rdi
0x1400df054  pop     rsi
0x1400df055  pop     r12
0x1400df057  pop     r14
0x1400df059  pop     r15
0x1400df05b  retn
0x1400df05c  dec     ebx; switch 4 cases
0x1400df05e  cmp     ebx, 3
0x1400df061  ja      def_1400DF075; jumptable 00000001400DF075 default case
0x1400df067  lea     rax, jpt_1400DF075
0x1400df06e  movsxd  rcx, ds:(jpt_1400DF075 - 1403CA380h)[rax+rbx*4]
0x1400df072  add     rcx, rax
0x1400df075  jmp     rcx; switch jump
0x1400df077  mov     rcx, rsi; jumptable 00000001400DF075 case 4
0x1400df07a  call    sub_1400B0000
0x1400df07f  mov     edi, eax
0x1400df081  jmp     short loc_1400DF023
0x1400df083  mov     rdi, [r14+8]; jumptable 00000001400DF075 case 3
0x1400df087  mov     r12, rdi
0x1400df08a  shr     r12, 20h
0x1400df08e  mov     ebp, 4
0x1400df093  mov     ebx, 2
0x1400df098  jmp     loc_1400DEF7D
0x1400df09d  mov     ebp, 4; jumptable 00000001400DF075 case 1
0x1400df0a2  mov     ebx, 2
0x1400df0a7  jmp     loc_1400DEF7A
0x1400df0ac  xor     eax, eax
0x1400df0ae  lea     rdi, [rsp+0E8h+var_A8]
0x1400df0b3  mov     [rdi], rax
0x1400df0b6  lea     r9, [rsp+0E8h+var_B8]
0x1400df0bb  mov     [r9], rax
0x1400df0be  lea     r12, [rsp+0E8h+var_AC]
0x1400df0c3  mov     qword ptr [rsp+0E8h+dwMaximumSizeLow], r12
0x1400df0c8  mov     r8, rdi
0x1400df0cb  call    sub_1400AFFA0
0x1400df0d0  mov     r14, [r14+8]
0x1400df0d4  movsxd  rax, dword ptr [r12]
0x1400df0d8  mov     rdx, rax
0x1400df0db  sar     rdx, 3Fh
0x1400df0df  add     rax, r14
0x1400df0e2  adc     rdx, 0
0x1400df0e6  mov     ecx, edx
0x1400df0e8  and     ecx, 1
0x1400df0eb  neg     rcx
0x1400df0ee  xor     rdx, rcx
0x1400df0f1  setnz   dl
0x1400df0f4  mov     rdi, [rdi]
0x1400df0f7  test    rdi, rdi
0x1400df0fa  js      loc_140170BB2
0x1400df100  test    dl, dl
0x1400df102  jnz     loc_140170BB2
0x1400df108  test    rcx, rcx
0x1400df10b  js      loc_140170BB2
0x1400df111  and     ecx, 1
0x1400df114  or      rcx, rax
0x1400df117  jz      loc_140170BB2
0x1400df11d  mov     r8, rdi
0x1400df120  shr     r8, 20h
0x1400df124  jmp     loc_1400DEFF4
0x140170ba2  mov     rcx, [rsp+0E8h+var_40]
0x140170baa  xor     rcx, rsp; StackCookie
0x140170bad  call    __security_check_cookie
0x140170bb2  xor     edi, edi
0x140170bb4  jmp     loc_1400DF023
0x140170bb9  xor     ebx, ebx; jumptable 00000001400DF075 default case
0x140170bbb  xor     ebp, ebp
0x140170bbd  jmp     loc_1400DEF7A
0x140170bc2  mov     ebp, 8; jumptable 00000001400DF075 case 2
0x140170bc7  mov     ebx, 1
0x140170bcc  jmp     loc_1400DEF7A
```
