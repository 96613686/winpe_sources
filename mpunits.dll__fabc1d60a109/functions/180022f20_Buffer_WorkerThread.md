# Buffer_WorkerThread

- ea: `0x180022f20`
- end: `0x180023122`
- name: `Buffer_WorkerThread`
- size: `514`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180008810`
- `0x180022f20`
- `0x180042ecc`
- `0x180043120`
- `0x1800431f0`
- `0x180044842`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002302d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002302d`

## pseudocode

```c
__int64 __fastcall Buffer_WorkerThread(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v3; // rax
  unsigned __int64 v4; // rcx
  __int128 v5; // xmm1
  unsigned int v6; // r8d
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  _OWORD v11[3]; // [rsp+20h] [rbp-39h] BYREF
  HMODULE hLibModule[2]; // [rsp+50h] [rbp-9h]
  _OWORD v13[2]; // [rsp+60h] [rbp+7h] BYREF

  v1 = *(_QWORD *)(a1 + 152);
  memset(v13, 0, sizeof(v13));
  ExecutionContext_SaveThread((LPGUID)v13);
  ExecutionContext_SetContext(*(GUID **)(a1 + 216));
  if ( !(unsigned int)TryAcquireWrite((unsigned __int64 *)(a1 + 184)) )
    QueueAcquireWrite(a1 + 184);
  if ( *(_QWORD *)(a1 + 208) == 1 )
    goto LABEL_17;
  *(_QWORD *)(a1 + 208) = 1;
  while ( 1 )
  {
    memset_0(v11, 0, 0x40u);
    v6 = *(_DWORD *)(a1 + 176);
    if ( *(_DWORD *)(a1 + 172) == v6 )
      break;
    v3 = *(_QWORD *)(a1 + 160);
    v4 = (unsigned __int64)(v6 % *(_DWORD *)(a1 + 168)) << 6;
    v11[0] = *(_OWORD *)(v4 + v3);
    v11[1] = *(_OWORD *)(v4 + v3 + 16);
    v11[2] = *(_OWORD *)(v4 + v3 + 32);
    v5 = *(_OWORD *)(v4 + v3 + 48);
    *(_DWORD *)(a1 + 176) = v6 + 1;
    *(_OWORD *)hLibModule = v5;
    ReadWriteLock_ReleaseWrite((volatile signed __int64 *)(a1 + 184));
    ((void (__fastcall *)(__int64, _OWORD *))ObserverProtocol_PostNext)(a1, v11);
    Item_Destruct(v11);
    if ( hLibModule[1] )
      FreeLibrary(hLibModule[1]);
    if ( !(unsigned int)TryAcquireWrite((unsigned __int64 *)(a1 + 184)) )
      QueueAcquireWrite(a1 + 184);
  }
  v7 = *(_DWORD *)(a1 + 192);
  *(_QWORD *)(a1 + 208) = 0;
  if ( v7 != 1 )
  {
LABEL_17:
    ReadWriteLock_ReleaseWrite((volatile signed __int64 *)(a1 + 184));
  }
  else
  {
    *(_DWORD *)(a1 + 192) = 2;
    ReadWriteLock_ReleaseWrite((volatile signed __int64 *)(a1 + 184));
    v8 = *(unsigned int *)(a1 + 196);
    if ( (_DWORD)v8 )
    {
      ((void (__fastcall *)(__int64, __int64, _QWORD))ObserverProtocol_PostErrorAndDispose)(
        a1,
        v8,
        *(_QWORD *)(a1 + 200));
      v9 = *(_QWORD *)(a1 + 200);
      if ( v9 && *(_QWORD *)v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    else
    {
      ((void (__fastcall *)(__int64))ObserverProtocol_PostCompleted)(a1);
    }
  }
  if ( v1 )
    (*(void (__fastcall **)(_QWORD))(v1 + 8))(*(_QWORD *)v1);
  return ((__int64 (__fastcall *)(_OWORD *))ExecutionContext_RestoreThread)(v13);
}

```

## disassembly

```asm
0x180022f20  push    rbp
0x180022f22  push    rbx
0x180022f23  push    rsi
0x180022f24  push    rdi
0x180022f25  lea     rbp, [rsp-3Fh]
0x180022f2a  sub     rsp, 98h
0x180022f31  mov     rax, cs:__security_cookie
0x180022f38  xor     rax, rsp
0x180022f3b  mov     [rbp+57h+var_30], rax
0x180022f3f  mov     rax, cs:off_180047C30
0x180022f46  xorps   xmm0, xmm0
0x180022f49  mov     rsi, [rcx+98h]
0x180022f50  mov     rbx, rcx
0x180022f53  movups  [rbp+57h+var_50], xmm0
0x180022f57  lea     rcx, [rbp+57h+var_50]
0x180022f5b  movups  [rbp+57h+var_40], xmm0
0x180022f5f  mov     rax, [rax]
0x180022f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f67  mov     rax, cs:off_180047C30
0x180022f6e  mov     rcx, [rbx+0D8h]
0x180022f75  mov     rax, [rax+10h]
0x180022f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f7e  lea     rdi, [rbx+0B8h]
0x180022f85  mov     rcx, rdi
0x180022f88  call    TryAcquireWrite
0x180022f8d  test    eax, eax
0x180022f8f  jnz     short loc_180022F99
0x180022f91  mov     rcx, rdi
0x180022f94  call    QueueAcquireWrite
0x180022f99  cmp     qword ptr [rbx+0D0h], 1
0x180022fa1  jz      loc_1800230DD
0x180022fa7  mov     qword ptr [rbx+0D0h], 1
0x180022fb2  jmp     loc_180023047
0x180022fb7  mov     eax, r8d
0x180022fba  xor     edx, edx
0x180022fbc  div     dword ptr [rbx+0A8h]
0x180022fc2  mov     rax, [rbx+0A0h]
0x180022fc9  mov     ecx, edx
0x180022fcb  shl     rcx, 6
0x180022fcf  movups  xmm0, xmmword ptr [rcx+rax]
0x180022fd3  movaps  [rbp+57h+var_90], xmm0
0x180022fd7  movups  xmm1, xmmword ptr [rcx+rax+10h]
0x180022fdc  movaps  [rbp+57h+var_80], xmm1
0x180022fe0  movups  xmm0, xmmword ptr [rcx+rax+20h]
0x180022fe5  movaps  [rbp+57h+var_70], xmm0
0x180022fe9  movups  xmm1, xmmword ptr [rcx+rax+30h]
0x180022fee  lea     eax, [r8+1]
0x180022ff2  mov     rcx, rdi
0x180022ff5  mov     [rbx+0B0h], eax
0x180022ffb  movaps  xmmword ptr [rbp+57h+hLibModule], xmm1
0x180022fff  call    ReadWriteLock_ReleaseWrite
0x180023004  mov     rax, cs:off_180047BB0
0x18002300b  lea     rdx, [rbp+57h+var_90]
0x18002300f  mov     rcx, rbx
0x180023012  mov     rax, [rax+20h]
0x180023016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002301b  lea     rcx, [rbp+57h+var_90]
0x18002301f  call    Item_Destruct
0x180023024  mov     rcx, [rbp+57h+hLibModule+8]; hLibModule
0x180023028  test    rcx, rcx
0x18002302b  jz      short loc_180023033
0x18002302d  call    cs:__imp_FreeLibrary
0x180023033  mov     rcx, rdi
0x180023036  call    TryAcquireWrite
0x18002303b  test    eax, eax
0x18002303d  jnz     short loc_180023047
0x18002303f  mov     rcx, rdi
0x180023042  call    QueueAcquireWrite
0x180023047  mov     r8d, 40h ; '@'; Size
0x18002304d  lea     rcx, [rbp+57h+var_90]; void *
0x180023051  xor     edx, edx; Val
0x180023053  call    memset_0
0x180023058  mov     r8d, [rbx+0B0h]
0x18002305f  cmp     [rbx+0ACh], r8d
0x180023066  jnz     loc_180022FB7
0x18002306c  mov     eax, [rbx+0C0h]
0x180023072  mov     qword ptr [rbx+0D0h], 0
0x18002307d  cmp     eax, 1
0x180023080  jnz     short loc_1800230DD
0x180023082  mov     rcx, rdi
0x180023085  mov     dword ptr [rbx+0C0h], 2
0x18002308f  call    ReadWriteLock_ReleaseWrite
0x180023094  mov     edx, [rbx+0C4h]
0x18002309a  mov     rcx, rbx
0x18002309d  mov     rax, cs:off_180047BB0
0x1800230a4  test    edx, edx
0x1800230a6  jnz     short loc_1800230AE
0x1800230a8  mov     rax, [rax+30h]
0x1800230ac  jmp     short loc_1800230D6
0x1800230ae  mov     r8, [rbx+0C8h]
0x1800230b5  mov     rax, [rax+60h]
0x1800230b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230be  mov     rcx, [rbx+0C8h]
0x1800230c5  test    rcx, rcx
0x1800230c8  jz      short loc_1800230E5
0x1800230ca  mov     rax, [rcx]
0x1800230cd  test    rax, rax
0x1800230d0  jz      short loc_1800230E5
0x1800230d2  mov     rax, [rax+10h]
0x1800230d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230db  jmp     short loc_1800230E5
0x1800230dd  mov     rcx, rdi
0x1800230e0  call    ReadWriteLock_ReleaseWrite
0x1800230e5  test    rsi, rsi
0x1800230e8  jz      short loc_1800230F6
0x1800230ea  mov     rcx, [rsi]
0x1800230ed  mov     rax, [rsi+8]
0x1800230f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230f6  mov     rax, cs:off_180047C30
0x1800230fd  lea     rcx, [rbp+57h+var_50]
0x180023101  mov     rax, [rax+8]
0x180023105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002310a  mov     rcx, [rbp+57h+var_30]
0x18002310e  xor     rcx, rsp; StackCookie
0x180023111  call    __security_check_cookie
0x180023116  add     rsp, 98h
0x18002311d  pop     rdi
0x18002311e  pop     rsi
0x18002311f  pop     rbx
0x180023120  pop     rbp
0x180023121  retn
```
