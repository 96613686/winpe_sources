# CPnpDiskCleanupHandler::GetSpaceUsed(unsigned __int64 *,IEmptyVolumeCacheCallBack *)

- ea: `0x180002fc0`
- end: `0x1800030ea`
- name: `?GetSpaceUsed@CPnpDiskCleanupHandler@@UEAAJPEA_KPEAUIEmptyVolumeCacheCallBack@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(CPnpDiskCleanupHandler *__hidden this, unsigned __int64 *, struct IEmptyVolumeCacheCallBack *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x180002fc0`
- `0x180006dc4`
- `0x180007dec`
- `0x18000a010`

## import_xrefs

- `SETUPAPI!pSetupIsUserAdmin` at `0x180002fef`
- `SETUPAPI!pSetupIsUserAdmin` at `0x180002fef`

## pseudocode

```c
__int64 __fastcall CPnpDiskCleanupHandler::GetSpaceUsed(
        CPnpDiskCleanupHandler *this,
        unsigned __int64 *a2,
        struct IEmptyVolumeCacheCallBack *a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int v8; // ebx
  int v9; // eax
  unsigned __int64 v10; // rcx
  __int128 v11; // [rsp+40h] [rbp-9h] BYREF
  __int128 v12; // [rsp+50h] [rbp+7h]
  __int128 v13; // [rsp+60h] [rbp+17h]
  __int64 v14; // [rsp+70h] [rbp+27h]

  v11 = 0;
  v14 = 0;
  v12 = 0;
  *a2 = 0;
  v13 = 0;
  if ( !(unsigned int)pSetupIsUserAdmin(this) )
    return 0;
  v8 = 1;
  LODWORD(v11) = 0;
  v12 = 0u;
  v13 = 0u;
  *((_QWORD *)&v11 + 1) = a3;
  LODWORD(v14) = 1;
  v9 = PnpCleanDriversEx(v6, v5, (__int64)PnpDiskCleanupStatusCallback, (__int64)&v11, 0, 0, 1);
  *((_QWORD *)&v12 + 1) += *((_QWORD *)&v13 + 1);
  *((_QWORD *)&v13 + 1) = 0;
  if ( !v9 )
  {
    LODWORD(v14) = 3;
    v9 = PnpCleanFiles((__int64)PnpDiskCleanupStatusCallback, (__int64)&v11, 0, 0, 1);
    v10 = *((_QWORD *)&v13 + 1) + *((_QWORD *)&v12 + 1);
    *((_QWORD *)&v12 + 1) += *((_QWORD *)&v13 + 1);
    *((_QWORD *)&v13 + 1) = 0;
    if ( !v9 )
    {
      if ( a3 )
      {
        ((void (__fastcall *)(struct IEmptyVolumeCacheCallBack *, unsigned __int64, __int64, _QWORD))a3->lpVtbl->ScanProgress)(
          a3,
          v10,
          1,
          0);
        v10 = *((_QWORD *)&v12 + 1);
      }
      *a2 = v10;
      return 0;
    }
  }
  if ( v9 == 1223 )
    return (unsigned int)-2147467260;
  return v8;
}

```

## disassembly

```asm
0x180002fc0  push    rbp
0x180002fc2  push    rbx
0x180002fc3  push    rsi
0x180002fc4  push    rdi
0x180002fc5  lea     rbp, [rsp-3Fh]
0x180002fca  sub     rsp, 88h
0x180002fd1  xorps   xmm0, xmm0
0x180002fd4  xor     eax, eax
0x180002fd6  movups  [rbp+57h+var_60], xmm0
0x180002fda  mov     [rbp+57h+var_30], rax
0x180002fde  mov     rdi, r8
0x180002fe1  movups  [rbp+57h+var_50], xmm0
0x180002fe5  mov     [rdx], rax
0x180002fe8  mov     rsi, rdx
0x180002feb  movups  [rbp+57h+var_40], xmm0
0x180002fef  call    cs:__imp_pSetupIsUserAdmin
0x180002ff5  test    eax, eax
0x180002ff7  jnz     short loc_180003000
0x180002ff9  xor     eax, eax
0x180002ffb  jmp     loc_1800030DE
0x180003000  mov     ebx, 1
0x180003005  mov     dword ptr [rbp+57h+var_60], 0
0x18000300c  mov     [rsp+0A0h+var_70], ebx
0x180003010  lea     r9, [rbp+57h+var_60]
0x180003014  mov     [rsp+0A0h+var_78], 0
0x18000301d  lea     r8, ?PnpDiskCleanupStatusCallback@@YAHPEAU_PNPCLEAN_STATUS_DATA@@PEAX@Z; PnpDiskCleanupStatusCallback(_PNPCLEAN_STATUS_DATA *,void *)
0x180003024  mov     [rsp+0A0h+var_80], 0
0x18000302d  mov     qword ptr [rbp+57h+var_50], 0
0x180003035  mov     qword ptr [rbp+57h+var_50+8], 0
0x18000303d  mov     qword ptr [rbp+57h+var_40], 0
0x180003045  mov     qword ptr [rbp+57h+var_40+8], 0
0x18000304d  mov     qword ptr [rbp+57h+var_60+8], rdi
0x180003051  mov     dword ptr [rbp+57h+var_30], ebx
0x180003054  call    PnpCleanDriversEx
0x180003059  mov     rdx, qword ptr [rbp+57h+var_40+8]
0x18000305d  add     qword ptr [rbp+57h+var_50+8], rdx
0x180003061  mov     qword ptr [rbp+57h+var_40+8], 0
0x180003069  test    eax, eax
0x18000306b  jnz     short loc_1800030CF
0x18000306d  xor     r9d, r9d
0x180003070  mov     dword ptr [rbp+57h+var_30], 3
0x180003077  xor     r8d, r8d
0x18000307a  mov     dword ptr [rsp+0A0h+var_80], ebx
0x18000307e  lea     rdx, [rbp+57h+var_60]
0x180003082  lea     rcx, ?PnpDiskCleanupStatusCallback@@YAHPEAU_PNPCLEAN_STATUS_DATA@@PEAX@Z; PnpDiskCleanupStatusCallback(_PNPCLEAN_STATUS_DATA *,void *)
0x180003089  call    PnpCleanFiles
0x18000308e  mov     rcx, qword ptr [rbp+57h+var_50+8]
0x180003092  add     rcx, qword ptr [rbp+57h+var_40+8]
0x180003096  mov     qword ptr [rbp+57h+var_50+8], rcx
0x18000309a  mov     qword ptr [rbp+57h+var_40+8], 0
0x1800030a2  test    eax, eax
0x1800030a4  jnz     short loc_1800030CF
0x1800030a6  test    rdi, rdi
0x1800030a9  jz      short loc_1800030C7
0x1800030ab  mov     rax, [rdi]
0x1800030ae  mov     rdx, rcx
0x1800030b1  xor     r9d, r9d
0x1800030b4  mov     r8d, ebx
0x1800030b7  mov     rcx, rdi
0x1800030ba  mov     rax, [rax+18h]
0x1800030be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c3  mov     rcx, qword ptr [rbp+57h+var_50+8]
0x1800030c7  mov     [rsi], rcx
0x1800030ca  jmp     loc_180002FF9
0x1800030cf  cmp     eax, 4C7h
0x1800030d4  mov     ecx, 80004004h
0x1800030d9  cmovz   ebx, ecx
0x1800030dc  mov     eax, ebx
0x1800030de  add     rsp, 88h
0x1800030e5  pop     rdi
0x1800030e6  pop     rsi
0x1800030e7  pop     rbx
0x1800030e8  pop     rbp
0x1800030e9  retn
```
