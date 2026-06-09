# MRxSmb2FsCtl

- ea: `0x14001cc00`
- end: `0x14001cf61`
- name: `MRxSmb2FsCtl`
- size: `865`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14001cb80`

## callees

- `0x140012450`
- `0x140012d80`
- `0x14001cc00`
- `0x14001e980`
- `0x1400218e0`
- `0x140028500`
- `0x14002b6f4`
- `0x14002b8ec`
- `0x14002b968`
- `0x14002fb78`
- `0x1400346c0`
- `0x140034ca4`
- `0x140034e78`
- `0x140050010`
- `0x1400506bc`
- `0x140050b90`
- `0x140051660`
- `0x140051788`
- `0x140051af4`
- `0x140056f20`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003bea8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003bea8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003be76`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003be76`
- `rdbss!RxLowIoCompletion` at `0x14003bdc3`
- `mrxsmb!SmbCeUpdateServerMultichannelConstraint` at `0x14001cdc4`
- `mrxsmb!SmbCeUpdateServerMultichannelConstraint` at `0x14001cdc4`
- `mrxsmb!MRxSmbCheckDevFcbXXXControlFileAccess` at `0x14003bf3a`
- `mrxsmb!MRxSmbCheckDevFcbXXXControlFileAccess` at `0x14003bf3a`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x14003be0c`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x14003be0c`
- `mrxsmb!SmbCseReleaseCompoundingKey` at `0x14003bdfd`
- `mrxsmb!SmbCseReleaseCompoundingKey` at `0x14003bdfd`
- `mrxsmb!SmbCseAllocateCompoundingKey` at `0x14003bdb7`
- `mrxsmb!SmbCseAllocateCompoundingKey` at `0x14003bdb7`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001cefe`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001cefe`

## pseudocode

```c
__int64 __fastcall MRxSmb2FsCtl(__int64 a1)
{
  char v1; // al
  unsigned int v3; // r9d
  unsigned int updated; // edi
  __int64 v6; // r8
  __int64 v7; // r10
  int v8; // ecx
  __int64 v9; // rax
  _DWORD *v10; // rdi
  __int64 CompoundingKey; // rsi
  _DWORD *v12; // r14
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rax
  unsigned __int64 v16; // rdx
  _WORD *v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rsi
  __int64 v20; // rax

  v1 = *(_BYTE *)(a1 + 576);
  v3 = *(_DWORD *)(a1 + 540);
  if ( v1 )
  {
    if ( v1 != 4 )
      return (unsigned int)-1073741808;
    if ( v3 == 1344075 )
      return (unsigned int)Smb2BatchedWrite(a1);
    if ( v3 != 1327699 )
      return (unsigned int)Smb2GenericFsControl(a1, v3, 0);
    return (unsigned int)Smb2BatchedRead(a1);
  }
  if ( v3 == 590328 )
    return (unsigned int)-1073741637;
  if ( v3 > 0x140200 )
  {
    switch ( v3 )
    {
      case 0x140204u:
        return Smb2QueryCompressedTraffic(a1);
      case 0x14038Cu:
        return (unsigned int)Smb2QueryRemoteServerName();
      case 0x1403F0u:
        return (unsigned int)MRxSmb2EnableTurboIoForFcb();
      case 0x1403F4u:
        v10 = *(_DWORD **)(a1 + 552);
        if ( !*(_BYTE *)(MRxSmbGetConfigurationBlock(a1) + 508) )
          return (unsigned int)-1073741637;
        if ( *(_DWORD *)(a1 + 568) >= 0xCu && *v10 == 12 )
          return (unsigned int)MRxSmb2WaitForMultichannelSetup(a1, v10);
        return (unsigned int)-1073741811;
    }
  }
  else
  {
    switch ( v3 )
    {
      case 0x140200u:
        return Smb2RequestCompressedTraffic();
      case 0x90478u:
        return (unsigned int)Smb2QueryRemoteFileSystemInformation();
      case 0x1401C8u:
        return (unsigned int)-1073741637;
      case 0x1401D0u:
        return (unsigned int)Smb2QueryStatistics();
      case 0x1401ECu:
        return (unsigned int)Smb2QueryDebugInformation(a1, 1311212);
      case 0x1401F0u:
        return (unsigned int)Smb2SetDebugInformation();
    }
  }
  v6 = *(_QWORD *)(a1 + 72);
  v7 = *(_QWORD *)(v6 + 40);
  if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v7 + 32) + 40LL) + 188LL) == 1 )
  {
    if ( v3 == 393620 || v3 == 393624 || v3 == 393648 )
    {
      return (unsigned int)Smb2DfsFsControl(a1, v3);
    }
    else if ( v3 == 1311228 )
    {
      return (unsigned int)Smb2GenericFsControl(a1, 1311228, 0);
    }
    else
    {
      return (unsigned int)Smb2NamedPipeFsControl(a1, v3);
    }
  }
  if ( v3 == 393624 )
    return (unsigned int)-1073741637;
  if ( v3 != 589992 )
  {
    if ( v3 <= 0x1401C4 )
    {
      if ( v3 == 1311172 )
      {
        CompoundingKey = SmbCseAllocateCompoundingKey(32);
        updated = Smb2PrefetchFileInformation(
                    a1,
                    CompoundingKey,
                    *(_QWORD *)(a1 + 552),
                    *(_DWORD *)(a1 + 568) >> 3,
                    RxLowIoCompletion);
        if ( CompoundingKey )
        {
          SmbCseReleaseCompoundingKey(CompoundingKey);
          SmbCseDereferenceCompoundingKey(CompoundingKey);
        }
        return updated;
      }
      if ( v3 > 0x110018 )
      {
        if ( v3 == 1130508 || v3 == 1163287 )
          return (unsigned int)-1073741637;
      }
      else
      {
        if ( v3 == 1114136 || v3 == 393620 || v3 == 393648 )
          return (unsigned int)-1073741637;
        if ( v3 == 590908 )
          return (unsigned int)Smb2ShareFlushAndPurge(a1);
      }
      return Smb2GenericFsControl(a1, v3, 0);
    }
    if ( v3 > 0x1403C8 )
    {
      if ( v3 != 1327692 )
      {
        if ( v3 == 1344068 )
          return (unsigned int)Smb2BatchedWrite(a1);
        return Smb2GenericFsControl(a1, v3, 0);
      }
      return (unsigned int)Smb2BatchedRead(a1);
    }
    switch ( v3 )
    {
      case 0x1403C8u:
        v16 = *(unsigned int *)(a1 + 568);
        v17 = *(_WORD **)(a1 + 552);
        if ( !(_DWORD)v16
          || (unsigned int)v16 >= 8
          && *v17 == 8
          && (v18 = (unsigned __int16)v17[1], (unsigned __int16)v18 <= 0x7FFFu)
          && v16 >= 4 * v18 + 4 )
        {
          v19 = *(_QWORD *)(*(_QWORD *)(v7 + 40) + 416LL);
          if ( (int)MRxSmbCheckDevFcbXXXControlFileAccess(1) < 0
            && (v20 = *(_QWORD *)(a1 + 40)) != 0
            && *(_BYTE *)(v20 + 64) )
          {
            return (unsigned int)-1073741790;
          }
          else
          {
            updated = SmbCeUpdateServerMultichannelConstraint();
            *(_QWORD *)(a1 + 184) = 0;
            v8 = *(_DWORD *)(v19 + 4);
            if ( (v8 & 8) == 0 )
            {
              v9 = *(_QWORD *)(v19 + 384);
              if ( *(_QWORD *)(v9 + 576) )
              {
                if ( (*(_DWORD *)(v9 + 4) & 1) != 0 && (v8 & 3) == 0 )
                  Smb2TryToEstablishMultipleChannelsImpl((PVOID)v19);
              }
            }
          }
          return updated;
        }
        break;
      case 0x1401CCu:
        return (unsigned int)Smb2ValidateAndReconnectSrvOpen(a1);
      case 0x1401D4u:
        return (unsigned int)Smb2RequestResiliency(a1);
      case 0x1401DCu:
        if ( *(_DWORD *)(a1 + 568) >= 8u )
        {
          v12 = *(_DWORD **)(a1 + 552);
          if ( !*v12 && (*(_DWORD *)(v6 + 128) & 8) != 0 )
          {
            v13 = *(_QWORD *)(v6 + 48);
            v14 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 56LL);
            ExAcquirePushLockExclusiveEx(v13 + 16, 0);
            v15 = (unsigned int)v12[1];
            if ( !(_DWORD)v15 )
              v15 = 1;
            *(_QWORD *)(v14 + 40) = 10000 * v15;
            *(_DWORD *)(v13 + 8) |= 0x100u;
            ExReleasePushLockExclusiveEx(v13 + 16, 0);
            *(_QWORD *)(a1 + 184) = 0;
            return 0;
          }
        }
        break;
      default:
        return Smb2GenericFsControl(a1, v3, 0);
    }
    return (unsigned int)-1073741811;
  }
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 56) + 355LL) & 0x3C) == 0x10
    && (*(_DWORD *)(*(_QWORD *)(v6 + 48) + 8LL) & 0x10000000) == 0 )
  {
    return (unsigned int)-1073741195;
  }
  return Smb2GenericFsControl(a1, 589992, 0);
}

```

## disassembly

```asm
0x14001cc00  push    rbx
0x14001cc02  push    rbp
0x14001cc03  push    rsi
0x14001cc04  push    rdi
0x14001cc05  push    r14
0x14001cc07  sub     rsp, 30h
0x14001cc0b  movzx   eax, byte ptr [rcx+240h]
0x14001cc12  mov     rbx, rcx
0x14001cc15  mov     r9d, [rcx+21Ch]
0x14001cc1c  test    al, al
0x14001cc1e  jnz     loc_14001CE1D
0x14001cc24  cmp     r9d, 901F8h
0x14001cc2b  jnz     short loc_14001CC40
0x14001cc2d  mov     edi, 0C00000BBh
0x14001cc32  mov     eax, edi
0x14001cc34  add     rsp, 30h
0x14001cc38  pop     r14
0x14001cc3a  pop     rdi
0x14001cc3b  pop     rsi
0x14001cc3c  pop     rbp
0x14001cc3d  pop     rbx
0x14001cc3e  retn
0x14001cc40  cmp     r9d, 140200h
0x14001cc47  ja      short loc_14001CC84
0x14001cc49  jz      loc_14001CD84
0x14001cc4f  mov     eax, r9d
0x14001cc52  sub     eax, 90478h
0x14001cc57  jz      loc_14001CE6E
0x14001cc5d  sub     eax, 0AFD50h
0x14001cc62  jz      short loc_14001CC2D
0x14001cc64  sub     eax, 8
0x14001cc67  jz      loc_14001CE62
0x14001cc6d  sub     eax, 1Ch
0x14001cc70  jz      loc_14001CE51
0x14001cc76  cmp     eax, 4
0x14001cc79  jnz     short loc_14001CCAF
0x14001cc7b  call    Smb2SetDebugInformation
0x14001cc80  mov     edi, eax
0x14001cc82  jmp     short loc_14001CC32
0x14001cc84  mov     eax, r9d
0x14001cc87  sub     eax, 140204h
0x14001cc8c  jz      loc_14001CF57
0x14001cc92  sub     eax, 188h
0x14001cc97  jz      loc_14001CF4B
0x14001cc9d  sub     eax, 64h ; 'd'
0x14001cca0  jz      loc_14001CF3F
0x14001cca6  cmp     eax, 4
0x14001cca9  jz      loc_14001CEF7
0x14001ccaf  mov     r8, [rcx+48h]
0x14001ccb3  mov     r10, [r8+28h]
0x14001ccb7  mov     rax, [r10+20h]
0x14001ccbb  mov     rcx, [rax+28h]
0x14001ccbf  cmp     byte ptr [rcx+0BCh], 1
0x14001ccc6  jz      loc_14001CEBA
0x14001cccc  cmp     r9d, 60198h
0x14001ccd3  jz      loc_14001CC2D
0x14001ccd9  cmp     r9d, 900A8h
0x14001cce0  jz      short loc_14001CD44
0x14001cce2  cmp     r9d, 1401C4h
0x14001cce9  ja      loc_14001CD95
0x14001ccef  jz      loc_14003BDB2
0x14001ccf5  cmp     r9d, 110018h
0x14001ccfc  ja      loc_14001CE89
0x14001cd02  jz      loc_14001CC2D
0x14001cd08  mov     eax, r9d
0x14001cd0b  sub     eax, 60194h
0x14001cd10  jz      loc_14001CC2D
0x14001cd16  sub     eax, 1Ch
0x14001cd19  jz      loc_14001CC2D
0x14001cd1f  cmp     eax, 3028Ch
0x14001cd24  jz      loc_14001CE7A
0x14001cd2a  xor     r8d, r8d
0x14001cd2d  mov     edx, r9d
0x14001cd30  mov     rcx, rbx
0x14001cd33  call    Smb2GenericFsControl
0x14001cd38  add     rsp, 30h
0x14001cd3c  pop     r14
0x14001cd3e  pop     rdi
0x14001cd3f  pop     rsi
0x14001cd40  pop     rbp
0x14001cd41  pop     rbx
0x14001cd42  retn
0x14001cd44  mov     rax, [rbx+38h]
0x14001cd48  movzx   ecx, byte ptr [rax+163h]
0x14001cd4f  and     cl, 3Ch
0x14001cd52  cmp     cl, 10h
0x14001cd55  jnz     short loc_14001CD68
0x14001cd57  mov     rax, [r8+30h]
0x14001cd5b  test    dword ptr [rax+8], 10000000h
0x14001cd62  jz      loc_14001CEB0
0x14001cd68  xor     r8d, r8d
0x14001cd6b  mov     edx, 900A8h
0x14001cd70  mov     rcx, rbx
0x14001cd73  call    Smb2GenericFsControl
0x14001cd78  add     rsp, 30h
0x14001cd7c  pop     r14
0x14001cd7e  pop     rdi
0x14001cd7f  pop     rsi
0x14001cd80  pop     rbp
0x14001cd81  pop     rbx
0x14001cd82  retn
0x14001cd84  call    Smb2RequestCompressedTraffic
0x14001cd89  add     rsp, 30h
0x14001cd8d  pop     r14
0x14001cd8f  pop     rdi
0x14001cd90  pop     rsi
0x14001cd91  pop     rbp
0x14001cd92  pop     rbx
0x14001cd93  retn
0x14001cd95  cmp     r9d, 1403C8h
0x14001cd9c  jbe     loc_14003BE1E
0x14001cda2  cmp     r9d, 14424Ch
0x14001cda9  jz      loc_14001CEA8
0x14001cdaf  cmp     r9d, 148244h
0x14001cdb6  jnz     loc_14001CD2A
0x14001cdbc  mov     rcx, rbx
0x14001cdbf  jmp     loc_14003BF87
0x14001cdc4  call    cs:__imp_SmbCeUpdateServerMultichannelConstraint
0x14001cdcb  nop     dword ptr [rax+rax+00h]
0x14001cdd0  mov     edi, eax
0x14001cdd2  xor     eax, eax
0x14001cdd4  mov     [rbx+0B8h], rax
0x14001cddb  mov     ecx, [rsi+4]
0x14001cdde  test    cl, 8
0x14001cde1  jnz     loc_14001CC32
0x14001cde7  mov     rax, [rsi+180h]
0x14001cdee  cmp     qword ptr [rax+240h], 0
0x14001cdf6  jz      loc_14001CC32
0x14001cdfc  mov     eax, [rax+4]
0x14001cdff  test    al, 1
0x14001ce01  jz      loc_14001CC32
0x14001ce07  test    cl, 3
0x14001ce0a  jnz     loc_14001CC32
0x14001ce10  mov     rcx, rsi; pContext
0x14001ce13  call    Smb2TryToEstablishMultipleChannelsImpl
0x14001ce18  jmp     loc_14001CC32
0x14001ce1d  cmp     al, 4
0x14001ce1f  jnz     loc_14003BDA8
0x14001ce25  cmp     r9d, 14824Bh
0x14001ce2c  jz      loc_14003BF87
0x14001ce32  cmp     r9d, 144253h
0x14001ce39  jz      loc_14003BF93
0x14001ce3f  xor     r8d, r8d
0x14001ce42  mov     edx, r9d
0x14001ce45  call    Smb2GenericFsControl
0x14001ce4a  mov     edi, eax
0x14001ce4c  jmp     loc_14001CC32
0x14001ce51  mov     edx, 1401ECh
0x14001ce56  call    Smb2QueryDebugInformation
0x14001ce5b  mov     edi, eax
0x14001ce5d  jmp     loc_14001CC32
0x14001ce62  call    Smb2QueryStatistics
0x14001ce67  mov     edi, eax
0x14001ce69  jmp     loc_14001CC32
0x14001ce6e  call    Smb2QueryRemoteFileSystemInformation
0x14001ce73  mov     edi, eax
0x14001ce75  jmp     loc_14001CC32
0x14001ce7a  mov     rcx, rbx
0x14001ce7d  call    Smb2ShareFlushAndPurge
0x14001ce82  mov     edi, eax
0x14001ce84  jmp     loc_14001CC32
0x14001ce89  cmp     r9d, 11400Ch
0x14001ce90  jz      loc_14001CC2D
0x14001ce96  cmp     r9d, 11C017h
0x14001ce9d  jz      loc_14001CC2D
0x14001cea3  jmp     loc_14001CD2A
0x14001cea8  mov     rcx, rbx
0x14001ceab  jmp     loc_14003BF93
0x14001ceb0  mov     edi, 0C0000275h
0x14001ceb5  jmp     loc_14001CC32
0x14001ceba  mov     eax, r9d
0x14001cebd  sub     eax, 60194h
0x14001cec2  jz      loc_14003BFB3
0x14001cec8  sub     eax, 4
0x14001cecb  jz      loc_14003BFB3
0x14001ced1  sub     eax, 18h
0x14001ced4  jz      loc_14003BFB3
0x14001ceda  mov     rcx, rbx
0x14001cedd  cmp     eax, 0E004Ch
0x14001cee2  jz      loc_14003BF9F
0x14001cee8  mov     edx, r9d
0x14001ceeb  call    Smb2NamedPipeFsControl
0x14001cef0  mov     edi, eax
0x14001cef2  jmp     loc_14001CC32
0x14001cef7  mov     rdi, [rcx+228h]
0x14001cefe  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001cf05  nop     dword ptr [rax+rax+00h]
0x14001cf0a  cmp     byte ptr [rax+1FCh], 0
0x14001cf11  jz      loc_14001CC2D
0x14001cf17  cmp     dword ptr [rbx+238h], 0Ch
0x14001cf1e  jb      loc_14003BEC4
0x14001cf24  cmp     dword ptr [rdi], 0Ch
0x14001cf27  jnz     loc_14003BEC4
0x14001cf2d  mov     rdx, rdi
0x14001cf30  mov     rcx, rbx
0x14001cf33  call    MRxSmb2WaitForMultichannelSetup
0x14001cf38  mov     edi, eax
0x14001cf3a  jmp     loc_14001CC32
0x14001cf3f  call    MRxSmb2EnableTurboIoForFcb
0x14001cf44  mov     edi, eax
0x14001cf46  jmp     loc_14001CC32
0x14001cf4b  call    Smb2QueryRemoteServerName
0x14001cf50  mov     edi, eax
0x14001cf52  jmp     loc_14001CC32
0x14001cf57  call    Smb2QueryCompressedTraffic
0x14001cf5c  jmp     loc_14001CD78
0x14003bda8  mov     edi, 0C0000010h
0x14003bdad  jmp     loc_14001CC32
0x14003bdb2  mov     ecx, 20h ; ' '
0x14003bdb7  call    cs:__imp_SmbCseAllocateCompoundingKey
0x14003bdbe  nop     dword ptr [rax+rax+00h]
0x14003bdc3  mov     rcx, cs:__imp_RxLowIoCompletion
0x14003bdca  mov     rdx, rax
0x14003bdcd  mov     r9d, [rbx+238h]
0x14003bdd4  mov     rsi, rax
0x14003bdd7  mov     r8, [rbx+228h]
0x14003bdde  mov     [rsp+58h+var_38], rcx
0x14003bde3  mov     rcx, rbx
0x14003bde6  shr     r9d, 3
0x14003bdea  call    Smb2PrefetchFileInformation
0x14003bdef  mov     edi, eax
0x14003bdf1  test    rsi, rsi
0x14003bdf4  jz      loc_14001CC32
0x14003bdfa  mov     rcx, rsi
0x14003bdfd  call    cs:__imp_SmbCseReleaseCompoundingKey
0x14003be04  nop     dword ptr [rax+rax+00h]
0x14003be09  mov     rcx, rsi
0x14003be0c  call    cs:__imp_SmbCseDereferenceCompoundingKey
0x14003be13  nop     dword ptr [rax+rax+00h]
0x14003be18  nop
0x14003be19  jmp     loc_14001CC32
0x14003be1e  jz      loc_14003BEEC
0x14003be24  mov     eax, r9d
0x14003be27  sub     eax, 1401CCh
0x14003be2c  jz      loc_14003BEDD
0x14003be32  sub     eax, 8
0x14003be35  jz      loc_14003BECE
0x14003be3b  cmp     eax, 8
0x14003be3e  jnz     loc_14001CD2A
0x14003be44  cmp     [rbx+238h], eax
0x14003be4a  jb      short loc_14003BEC4
0x14003be4c  mov     r14, [rbx+228h]
0x14003be53  cmp     dword ptr [r14], 0
0x14003be57  jnz     short loc_14003BEC4
0x14003be59  mov     eax, [r8+80h]
0x14003be60  test    al, 8
0x14003be62  jz      short loc_14003BEC4
0x14003be64  mov     rsi, [r8+30h]
0x14003be68  xor     edx, edx
0x14003be6a  mov     rax, [rbx+40h]
0x14003be6e  lea     rcx, [rsi+10h]
0x14003be72  mov     rdi, [rax+38h]
0x14003be76  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003be7d  nop     dword ptr [rax+rax+00h]
0x14003be82  mov     eax, [r14+4]
0x14003be86  mov     ecx, 1
0x14003be8b  cmp     eax, ecx
0x14003be8d  cmovb   eax, ecx
0x14003be90  xor     edx, edx
0x14003be92  imul    rax, 2710h
0x14003be99  lea     rcx, [rsi+10h]
0x14003be9d  mov     [rdi+28h], rax
0x14003bea1  or      dword ptr [rsi+8], 100h
0x14003bea8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003beaf  nop     dword ptr [rax+rax+00h]
0x14003beb4  xor     eax, eax
0x14003beb6  mov     [rbx+0B8h], rax
0x14003bebd  mov     edi, eax
0x14003bebf  jmp     loc_14001CC32
0x14003bec4  mov     edi, 0C000000Dh
0x14003bec9  jmp     loc_14001CC32
0x14003bece  mov     rcx, rbx
0x14003bed1  call    Smb2RequestResiliency
0x14003bed6  mov     edi, eax
0x14003bed8  jmp     loc_14001CC32
0x14003bedd  mov     rcx, rbx
0x14003bee0  call    Smb2ValidateAndReconnectSrvOpen
0x14003bee5  mov     edi, eax
0x14003bee7  jmp     loc_14001CC32
0x14003beec  mov     edx, [rbx+238h]
0x14003bef2  mov     rdi, [rbx+228h]
0x14003bef9  test    edx, edx
0x14003befb  jz      short loc_14003BF23
0x14003befd  cmp     edx, 8
0x14003bf00  jb      short loc_14003BEC4
0x14003bf02  cmp     word ptr [rdi], 8
0x14003bf06  jnz     short loc_14003BEC4
0x14003bf08  movzx   eax, word ptr [rdi+2]
0x14003bf0c  mov     ecx, 7FFFh
0x14003bf11  cmp     ax, cx
0x14003bf14  ja      short loc_14003BEC4
0x14003bf16  lea     rcx, ds:4[rax*4]
0x14003bf1e  cmp     rdx, rcx
0x14003bf21  jb      short loc_14003BEC4
0x14003bf23  mov     rax, [r10+28h]
0x14003bf27  mov     ecx, 1
0x14003bf2c  mov     rsi, [rax+1A0h]
0x14003bf33  mov     rbp, [rsi+180h]
0x14003bf3a  call    cs:__imp_MRxSmbCheckDevFcbXXXControlFileAccess
0x14003bf41  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
