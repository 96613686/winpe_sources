# FveLoadFveMetadataPrepInfo

- ea: `0x14006b690`
- end: `0x14006baff`
- name: `FveLoadFveMetadataPrepInfo`
- size: `1135`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14008e180`

## callees

- `0x140006ee0`
- `0x140008dc0`
- `0x140008e44`
- `0x140021d00`
- `0x14006b690`
- `0x140087bf0`
- `0x1400909ec`

## import_xrefs

- `ntoskrnl!ZwReadFile` at `0x14006b87a`
- `ntoskrnl!ZwReadFile` at `0x14006b87a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b920`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b920`
- `ntoskrnl!ExAllocatePool2` at `0x14006b733`
- `ntoskrnl!ExAllocatePool2` at `0x14006b733`

## pseudocode

```c
__int64 __fastcall FveLoadFveMetadataPrepInfo(__int64 a1, __int64 a2)
{
  unsigned int v2; // esi
  NTSTATUS Status; // ebp
  ULONG Length; // esi
  _QWORD *Pool2; // rax
  _QWORD *Buffer; // rdi
  int v9; // eax
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // ebx
  int v15; // eax
  unsigned __int64 v16; // rcx
  unsigned int v17; // r8d
  bool v18; // zf
  unsigned __int64 v19; // r9
  unsigned __int64 v20; // r10
  __int64 v21; // r11
  bool v22; // zf
  unsigned __int64 v23; // rcx
  bool v24; // zf
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-38h] BYREF
  HANDLE FileHandle; // [rsp+A8h] [rbp+10h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+B0h] [rbp+18h] BYREF

  v2 = *(_DWORD *)(a2 + 108);
  Status = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  ByteOffset.QuadPart = 0;
  if ( ((v2 - 1) & v2) != 0 || !v2 )
  {
    if ( 0x48 % v2 )
      Length = v2 - 0x48 % v2 + 72;
    else
      Length = 72;
  }
  else
  {
    Length = ~(v2 - 1) & (v2 + 71);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 256, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids);
  }
  if ( !*(_QWORD *)(a2 + 128) )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(264, Length, 809850438);
    Buffer = Pool2;
    if ( !Pool2 )
    {
      Status = -1073741670;
      goto LABEL_14;
    }
    memset(Pool2, 0, 0x48u);
    *(_QWORD *)(a2 + 128) = Buffer;
    v9 = FveFileOpenEx(
           (PCUNICODE_STRING)a2,
           (GUID *)&FVE_PREP_FILE_TYPE_GUID,
           0,
           (__int64)L"FVE2.",
           0,
           3u,
           1u,
           0x886Au,
           1,
           0,
           0,
           &FileHandle);
    Status = v9;
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v11 = 257;
        v12 = (unsigned int)v9;
LABEL_33:
        WPP_SF_d(v10->AttachedDevice, v11, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids, v12);
      }
LABEL_34:
      if ( *(_QWORD **)(a2 + 128) == Buffer )
        *(_QWORD *)(a2 + 128) = 0;
LABEL_36:
      ExFreePoolWithTag(Buffer, 0x30455646u);
LABEL_37:
      if ( FileHandle )
        FveFileClose(FileHandle);
      goto LABEL_14;
    }
    Status = ZwReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0);
    if ( Status >= 0 )
    {
      Status = IoStatusBlock.Status;
      if ( IoStatusBlock.Status >= 0 )
      {
        if ( IoStatusBlock.Information == Length )
        {
          v14 = *((_DWORD *)Buffer + 2);
          *((_DWORD *)Buffer + 2) = 0;
          v15 = ComputeCrc32(v13, Buffer, Length);
          *((_DWORD *)Buffer + 2) = v15;
          if ( v15 != v14 )
          {
            Status = -1073741279;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_34;
            }
            v11 = 259;
            goto LABEL_32;
          }
          if ( *Buffer != 0x50455250455646LL )
            goto LABEL_68;
          if ( *((_WORD *)Buffer + 6) != 1 )
            goto LABEL_68;
          if ( *((_WORD *)Buffer + 7) != 72 )
            goto LABEL_68;
          if ( (unsigned __int16)(*((_WORD *)Buffer + 8) - 1) > 0xFu )
            goto LABEL_68;
          v16 = *((unsigned int *)Buffer + 6);
          if ( *((unsigned __int16 *)Buffer + 9) > (unsigned int)v16 )
            goto LABEL_68;
          if ( *((_DWORD *)Buffer + 7) != *(_DWORD *)(a2 + 108) )
            goto LABEL_68;
          if ( *((_DWORD *)Buffer + 8) != 0x10000 )
            goto LABEL_68;
          if ( *((_DWORD *)Buffer + 9) != 0x10000 )
            goto LABEL_68;
          if ( *((_DWORD *)Buffer + 10) != 0x100000 )
            goto LABEL_68;
          v17 = *((_DWORD *)Buffer + 11);
          if ( !v17 )
            goto LABEL_68;
          v18 = (((_DWORD)v16 - 1) & (unsigned int)v16) != 0 || !(_DWORD)v16
              ? v17 % (unsigned int)v16 == 0
              : (((_DWORD)v16 - 1) & v17) == 0;
          if ( !v18
            || !*((_DWORD *)Buffer + 12)
            || (v19 = Buffer[7]) == 0
            || ((v20 = v16 - 1, (v21 = v16 & (v16 - 1)) != 0) || !(_DWORD)v16
              ? (v22 = v19 % v16 == 0)
              : (v22 = (v20 & v19) == 0),
                !v22
             || (v23 = Buffer[8]) == 0
             || (v21 || !*((_DWORD *)Buffer + 6)
               ? (v24 = v23 % *((unsigned int *)Buffer + 6) == 0)
               : (v24 = (v23 & v20) == 0),
                 !v24 || v23 < 0x2000)) )
          {
LABEL_68:
            Status = -1071579134;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_34;
            }
            v11 = 260;
LABEL_32:
            v12 = (unsigned int)Status;
            goto LABEL_33;
          }
LABEL_78:
          if ( *(_QWORD **)(a2 + 128) == Buffer )
            Buffer = 0;
          if ( !Buffer )
            goto LABEL_37;
          goto LABEL_36;
        }
        Status = -1073741823;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        258,
        WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids,
        (unsigned int)Status);
    }
    if ( Status < 0 )
      goto LABEL_34;
    goto LABEL_78;
  }
LABEL_14:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      261,
      WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids,
      (unsigned int)Status);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14006b690  mov     rax, rsp
0x14006b693  mov     [rax+20h], rbx
0x14006b697  push    rbp
0x14006b698  push    rsi
0x14006b699  push    rdi
0x14006b69a  push    r13
0x14006b69c  push    r14
0x14006b69e  sub     rsp, 70h
0x14006b6a2  mov     esi, [rdx+6Ch]
0x14006b6a5  xor     ebp, ebp
0x14006b6a7  xorps   xmm0, xmm0
0x14006b6aa  mov     [rax+10h], rbp
0x14006b6ae  movups  xmmword ptr [rax-38h], xmm0
0x14006b6b2  mov     [rax+18h], rbp
0x14006b6b6  mov     r14, rdx
0x14006b6b9  lea     eax, [rsi-1]
0x14006b6bc  lea     r13d, [rbp+48h]
0x14006b6c0  test    esi, eax
0x14006b6c2  jnz     short loc_14006B6D1
0x14006b6c4  test    esi, esi
0x14006b6c6  jz      short loc_14006B6D1
0x14006b6c8  add     esi, 47h ; 'G'
0x14006b6cb  not     eax
0x14006b6cd  and     esi, eax
0x14006b6cf  jmp     short loc_14006B6E6
0x14006b6d1  xor     edx, edx
0x14006b6d3  mov     eax, r13d
0x14006b6d6  div     esi
0x14006b6d8  test    edx, edx
0x14006b6da  jnz     short loc_14006B6E1
0x14006b6dc  mov     esi, r13d
0x14006b6df  jmp     short loc_14006B6E6
0x14006b6e1  sub     esi, edx
0x14006b6e3  add     esi, r13d
0x14006b6e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b6ed  lea     rax, WPP_GLOBAL_Control
0x14006b6f4  cmp     rcx, rax
0x14006b6f7  jz      short loc_14006B71B
0x14006b6f9  mov     eax, [rcx+2Ch]
0x14006b6fc  test    al, 20h
0x14006b6fe  jz      short loc_14006B71B
0x14006b700  cmp     byte ptr [rcx+29h], 5
0x14006b704  jb      short loc_14006B71B
0x14006b706  mov     rcx, [rcx+18h]
0x14006b70a  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006b711  mov     edx, 100h
0x14006b716  call    WPP_SF_
0x14006b71b  cmp     [r14+80h], rbp
0x14006b722  jnz     short loc_14006B74C
0x14006b724  mov     r8d, 30455646h
0x14006b72a  mov     edx, esi
0x14006b72c  mov     ecx, 108h
0x14006b731  mov     ebx, esi
0x14006b733  call    cs:__imp_ExAllocatePool2
0x14006b73a  nop     dword ptr [rax+rax+00h]
0x14006b73f  mov     rdi, rax
0x14006b742  test    rax, rax
0x14006b745  jnz     short loc_14006B79B
0x14006b747  mov     ebp, 0C000009Ah
0x14006b74c  lea     rbx, WPP_GLOBAL_Control
0x14006b753  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b75a  cmp     rcx, rbx
0x14006b75d  jz      short loc_14006B784
0x14006b75f  mov     eax, [rcx+2Ch]
0x14006b762  test    al, 20h
0x14006b764  jz      short loc_14006B784
0x14006b766  cmp     byte ptr [rcx+29h], 5
0x14006b76a  jb      short loc_14006B784
0x14006b76c  mov     rcx, [rcx+18h]
0x14006b770  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006b777  mov     edx, 105h
0x14006b77c  mov     r9d, ebp
0x14006b77f  call    WPP_SF_d
0x14006b784  mov     rbx, [rsp+98h+arg_18]
0x14006b78c  mov     eax, ebp
0x14006b78e  add     rsp, 70h
0x14006b792  pop     r14
0x14006b794  pop     r13
0x14006b796  pop     rdi
0x14006b797  pop     rsi
0x14006b798  pop     rbp
0x14006b799  retn
0x14006b79b  mov     r8, r13; Size
0x14006b79e  xor     edx, edx; Val
0x14006b7a0  mov     rcx, rdi; void *
0x14006b7a3  call    memset
0x14006b7a8  lea     rax, [rsp+98h+FileHandle]
0x14006b7b0  mov     [r14+80h], rdi
0x14006b7b7  mov     [rsp+98h+var_40], rax; __int64
0x14006b7bc  lea     r9, aFve2; "FVE2."
0x14006b7c3  mov     [rsp+98h+var_48], rbp; __int64
0x14006b7c8  lea     rdx, FVE_PREP_FILE_TYPE_GUID; Guid
0x14006b7cf  mov     [rsp+98h+var_50], rbp; __int64
0x14006b7d4  mov     eax, 1
0x14006b7d9  mov     byte ptr [rsp+98h+Key], al; char
0x14006b7dd  xor     r8d, r8d
0x14006b7e0  mov     dword ptr [rsp+98h+ByteOffset], 886Ah; ULONG
0x14006b7e8  mov     rcx, r14; SourceString
0x14006b7eb  mov     [rsp+98h+Length], eax; ULONG
0x14006b7ef  mov     dword ptr [rsp+98h+Buffer], 3; ULONG
0x14006b7f7  mov     byte ptr [rsp+98h+IoStatusBlock], bpl; char
0x14006b7fc  call    FveFileOpenEx
0x14006b801  mov     ebp, eax
0x14006b803  test    eax, eax
0x14006b805  jns     short loc_14006B841
0x14006b807  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b80e  lea     rbx, WPP_GLOBAL_Control
0x14006b815  cmp     rcx, rbx
0x14006b818  jz      loc_14006B904
0x14006b81e  mov     edx, [rcx+2Ch]
0x14006b821  test    dl, 20h
0x14006b824  jz      loc_14006B904
0x14006b82a  cmp     byte ptr [rcx+29h], 2
0x14006b82e  jb      loc_14006B904
0x14006b834  mov     edx, 101h
0x14006b839  mov     r9d, eax
0x14006b83c  jmp     loc_14006B8F4
0x14006b841  mov     rcx, [rsp+98h+FileHandle]; FileHandle
0x14006b849  lea     rax, [rsp+98h+arg_10]
0x14006b851  mov     [rsp+98h+Key], 0; Key
0x14006b85a  xor     r9d, r9d; ApcContext
0x14006b85d  mov     [rsp+98h+ByteOffset], rax; ByteOffset
0x14006b862  xor     r8d, r8d; ApcRoutine
0x14006b865  mov     [rsp+98h+Length], esi; Length
0x14006b869  lea     rax, [rsp+98h+var_38]
0x14006b86e  mov     [rsp+98h+Buffer], rdi; Buffer
0x14006b873  xor     edx, edx; Event
0x14006b875  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x14006b87a  call    cs:__imp_ZwReadFile
0x14006b881  nop     dword ptr [rax+rax+00h]
0x14006b886  mov     ebp, eax
0x14006b888  test    eax, eax
0x14006b88a  js      loc_14006BA9B
0x14006b890  mov     ebp, dword ptr [rsp+98h+var_38]
0x14006b894  test    ebp, ebp
0x14006b896  js      loc_14006BA9B
0x14006b89c  cmp     [rsp+98h+var_38.Information], rbx
0x14006b8a1  jnz     loc_14006BA96
0x14006b8a7  mov     ebx, [rdi+8]
0x14006b8aa  mov     r8d, esi
0x14006b8ad  mov     rdx, rdi
0x14006b8b0  mov     dword ptr [rdi+8], 0
0x14006b8b7  call    ComputeCrc32
0x14006b8bc  mov     [rdi+8], eax
0x14006b8bf  cmp     eax, ebx
0x14006b8c1  jz      loc_14006B94F
0x14006b8c7  mov     ebp, 0C0000221h
0x14006b8cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b8d3  lea     rbx, WPP_GLOBAL_Control
0x14006b8da  cmp     rcx, rbx
0x14006b8dd  jz      short loc_14006B904
0x14006b8df  mov     eax, [rcx+2Ch]
0x14006b8e2  test    al, 20h
0x14006b8e4  jz      short loc_14006B904
0x14006b8e6  cmp     byte ptr [rcx+29h], 2
0x14006b8ea  jb      short loc_14006B904
0x14006b8ec  mov     edx, 103h
0x14006b8f1  mov     r9d, ebp
0x14006b8f4  mov     rcx, [rcx+18h]
0x14006b8f8  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006b8ff  call    WPP_SF_d
0x14006b904  cmp     [r14+80h], rdi
0x14006b90b  jnz     short loc_14006B918
0x14006b90d  mov     qword ptr [r14+80h], 0
0x14006b918  mov     edx, 30455646h; Tag
0x14006b91d  mov     rcx, rdi; P
0x14006b920  call    cs:__imp_ExFreePoolWithTag
0x14006b927  nop     dword ptr [rax+rax+00h]
0x14006b92c  cmp     [rsp+98h+FileHandle], 0
0x14006b935  jz      loc_14006B753
0x14006b93b  mov     rcx, [rsp+98h+FileHandle]; FileHandle
0x14006b943  xor     edx, edx
0x14006b945  call    FveFileClose
0x14006b94a  jmp     loc_14006B753
0x14006b94f  mov     rcx, 50455250455646h
0x14006b959  cmp     [rdi], rcx
0x14006b95c  jnz     loc_14006BA5B
0x14006b962  mov     ecx, 1
0x14006b967  cmp     [rdi+0Ch], cx
0x14006b96b  jnz     loc_14006BA5B
0x14006b971  cmp     [rdi+0Eh], r13w
0x14006b976  jnz     loc_14006BA5B
0x14006b97c  movzx   eax, word ptr [rdi+10h]
0x14006b980  sub     ax, cx
0x14006b983  cmp     ax, 0Fh
0x14006b987  ja      loc_14006BA5B
0x14006b98d  mov     ecx, [rdi+18h]
0x14006b990  movzx   eax, word ptr [rdi+12h]
0x14006b994  cmp     eax, ecx
0x14006b996  ja      loc_14006BA5B
0x14006b99c  mov     eax, [r14+6Ch]
0x14006b9a0  cmp     [rdi+1Ch], eax
0x14006b9a3  jnz     loc_14006BA5B
0x14006b9a9  mov     eax, 10000h
0x14006b9ae  cmp     [rdi+20h], eax
0x14006b9b1  jnz     loc_14006BA5B
0x14006b9b7  cmp     [rdi+24h], eax
0x14006b9ba  jnz     loc_14006BA5B
0x14006b9c0  cmp     dword ptr [rdi+28h], 100000h
0x14006b9c7  jnz     loc_14006BA5B
0x14006b9cd  mov     r8d, [rdi+2Ch]
0x14006b9d1  test    r8d, r8d
0x14006b9d4  jz      loc_14006BA5B
0x14006b9da  lea     eax, [rcx-1]
0x14006b9dd  test    ecx, eax
0x14006b9df  jnz     short loc_14006B9EA
0x14006b9e1  test    ecx, ecx
0x14006b9e3  jz      short loc_14006B9EA
0x14006b9e5  test    r8d, eax
0x14006b9e8  jmp     short loc_14006B9F3
0x14006b9ea  xor     edx, edx
0x14006b9ec  mov     eax, r8d
0x14006b9ef  div     ecx
0x14006b9f1  test    edx, edx
0x14006b9f3  jnz     short loc_14006BA5B
0x14006b9f5  cmp     dword ptr [rdi+30h], 0
0x14006b9f9  jz      short loc_14006BA5B
0x14006b9fb  mov     r9, [rdi+38h]
0x14006b9ff  test    r9, r9
0x14006ba02  jz      short loc_14006BA5B
0x14006ba04  lea     r10, [rcx-1]
0x14006ba08  mov     r8, rcx
0x14006ba0b  mov     r11, r10
0x14006ba0e  and     r11, rcx
0x14006ba11  jnz     short loc_14006BA1C
0x14006ba13  test    ecx, ecx
0x14006ba15  jz      short loc_14006BA1C
0x14006ba17  test    r9, r10
0x14006ba1a  jmp     short loc_14006BA27
0x14006ba1c  xor     edx, edx
0x14006ba1e  mov     rax, r9
0x14006ba21  div     r8
0x14006ba24  test    rdx, rdx
0x14006ba27  jnz     short loc_14006BA5B
0x14006ba29  mov     rcx, [rdi+40h]
0x14006ba2d  test    rcx, rcx
0x14006ba30  jz      short loc_14006BA5B
0x14006ba32  test    r11, r11
0x14006ba35  jnz     short loc_14006BA41
0x14006ba37  test    r8, r8
0x14006ba3a  jz      short loc_14006BA41
0x14006ba3c  test    r10, rcx
0x14006ba3f  jmp     short loc_14006BA4C
0x14006ba41  xor     edx, edx
0x14006ba43  mov     rax, rcx
0x14006ba46  div     r8
0x14006ba49  test    rdx, rdx
0x14006ba4c  jnz     short loc_14006BA5B
0x14006ba4e  cmp     rcx, 2000h
0x14006ba55  jnb     loc_14006BADD
0x14006ba5b  mov     ebp, 0C0210002h
0x14006ba60  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ba67  lea     rbx, WPP_GLOBAL_Control
0x14006ba6e  cmp     rcx, rbx
0x14006ba71  jz      loc_14006B904
0x14006ba77  mov     eax, [rcx+2Ch]
0x14006ba7a  test    al, 20h
0x14006ba7c  jz      loc_14006B904
0x14006ba82  cmp     byte ptr [rcx+29h], 2
0x14006ba86  jb      loc_14006B904
0x14006ba8c  mov     edx, 104h
0x14006ba91  jmp     loc_14006B8F1
0x14006ba96  mov     ebp, 0C0000001h
0x14006ba9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006baa2  lea     rbx, WPP_GLOBAL_Control
0x14006baa9  cmp     rcx, rbx
0x14006baac  jz      short loc_14006BAD3
0x14006baae  mov     eax, [rcx+2Ch]
0x14006bab1  test    al, 20h
0x14006bab3  jz      short loc_14006BAD3
0x14006bab5  cmp     byte ptr [rcx+29h], 2
0x14006bab9  jb      short loc_14006BAD3
0x14006babb  mov     rcx, [rcx+18h]
0x14006babf  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006bac6  mov     edx, 102h
0x14006bacb  mov     r9d, ebp
0x14006bace  call    WPP_SF_d
0x14006bad3  test    ebp, ebp
0x14006bad5  js      loc_14006B904
0x14006badb  jmp     short loc_14006BAE4
0x14006badd  lea     rbx, WPP_GLOBAL_Control
0x14006bae4  xor     eax, eax
0x14006bae6  cmp     [r14+80h], rdi
0x14006baed  cmovz   rdi, rax
0x14006baf1  test    rdi, rdi
0x14006baf4  jz      loc_14006B92C
0x14006bafa  jmp     loc_14006B918
```
