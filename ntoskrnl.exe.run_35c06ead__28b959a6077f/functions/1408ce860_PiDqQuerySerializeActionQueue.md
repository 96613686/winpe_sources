# PiDqQuerySerializeActionQueue

- ea: `0x1408ce860`
- end: `0x1408ceb72`
- name: `PiDqQuerySerializeActionQueue`
- size: `786`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1408cf0a0`
- `0x1408d078c`

## callees

- `0x1408ce290`
- `0x1408ce860`
- `0x1408ceb78`
- `0x1408cfdf0`
- `0x1408cfe60`
- `0x1408d02f8`
- `0x1408d0a3c`
- `0x1408d0a7c`
- `0x140bae8e0`

## import_xrefs

- `msrpc!MesHandleFree` at `0x1408ceaf9`
- `msrpc!MesHandleFree` at `0x1408ceaf9`
- `msrpc!MesEncodeIncrementalHandleCreate` at `0x1408ce8ff`
- `msrpc!MesEncodeIncrementalHandleCreate` at `0x1408ce8ff`
- `msrpc!MesIncrementalHandleReset` at `0x1408ce938`
- `msrpc!MesIncrementalHandleReset` at `0x1408ce938`
- `msrpc!NdrMesTypeEncode3` at `0x1408ce9cf`
- `msrpc!NdrMesTypeEncode3` at `0x1408ce9cf`

## pseudocode

```c
__int64 __fastcall PiDqQuerySerializeActionQueue(__int64 a1, __int64 a2, int a3, char a4, int *a5, _DWORD *a6)
{
  int v7; // esi
  int v8; // ebx
  struct _ERESOURCE *ObjectManager; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // r15
  __int64 v12; // rcx
  int v13; // ebx
  _QWORD v15[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v16; // [rsp+40h] [rbp-48h] BYREF
  int v17; // [rsp+48h] [rbp-40h]
  int v18; // [rsp+4Ch] [rbp-3Ch]
  PVOID P; // [rsp+50h] [rbp-38h]
  int v20; // [rsp+58h] [rbp-30h]
  bool v21; // [rsp+5Ch] [rbp-2Ch]
  char v22; // [rsp+5Dh] [rbp-2Bh]
  __int16 v23; // [rsp+5Eh] [rbp-2Ah]
  PVOID v24; // [rsp+98h] [rbp+10h] BYREF

  v7 = 0;
  v15[0] = 0;
  v24 = 0;
  v23 = 0;
  v16 = a2;
  v17 = a3;
  v18 = 16;
  P = 0;
  v20 = 0;
  v21 = (a4 & 3) == 3;
  v22 = 0;
  PiDqQueryLock(a1);
  v8 = *(_DWORD *)(a1 + 216);
  PiDqQueryUnlock(a1);
  if ( (v8 & 0x20) == 0 )
  {
    ObjectManager = (struct _ERESOURCE *)PiDqQueryGetObjectManager(a1);
    v7 = PiDqObjectManagerEnumerateAndRegisterQuery(ObjectManager);
  }
  if ( v7 < 0 )
  {
LABEL_18:
    *a5 = 0;
    *a6 = 0;
  }
  else
  {
    v7 = MesEncodeIncrementalHandleCreate(&v16, PiDqSerializationAlloc, &PiDqSerializationWrite, v15);
    if ( v7 >= 0 )
    {
      v7 = MesIncrementalHandleReset(v15[0], &v16, 0, 0, 0, *(_DWORD *)(a1 + 216) & 2);
      if ( v7 >= 0 )
      {
        *a5 = v18;
        *a6 = 0;
        PiDqQueryLock(a1);
        v15[1] = a1 + 184;
        v24 = *(PVOID *)(a1 + 184);
        *(_QWORD *)(a1 + 184) = 0;
        PiDqQueryUnlock(a1);
        while ( 1 )
        {
          if ( v24 )
          {
            NdrMesTypeEncode3(v15[0], "TP 3\a", &off_140004F60, &off_140E0A510, 1, &v24);
            if ( (_BYTE)v23 )
            {
              v7 = -1073741819;
              goto LABEL_18;
            }
            if ( v22 )
            {
              PiDqQueryLock(a1);
              *(_QWORD *)(a1 + 184) = v24;
              v24 = 0;
              PiDqQueryUnlock(a1);
              *a6 = v20 + 16;
              break;
            }
            *a5 = v18;
            PiDqActionDataFree(v24);
            v24 = 0;
          }
          PiDqQueryLock(a1);
          v10 = (_QWORD *)(a1 + 192);
          v11 = *(_QWORD **)(a1 + 192);
          if ( v11 == (_QWORD *)(a1 + 192) )
          {
            PiDqQueryUnlock(a1);
            break;
          }
          if ( (_QWORD *)v11[1] != v10 || (v12 = *v11, *(_QWORD **)(*v11 + 8LL) != v11) )
            __fastfail(3u);
          *v10 = v12;
          *(_QWORD *)(v12 + 8) = v10;
          --*(_DWORD *)(a1 + 208);
          PiDqQueryUnlock(a1);
          v13 = PiDqActionDataCreate(*(_QWORD *)(a1 + 24), a1 + 32, v11, &v24);
          PiDqQueryActionQueueEntryFree(v11);
          v7 = 0;
          if ( v13 != -1073741772 )
            v7 = v13;
          if ( v7 < 0 )
            goto LABEL_18;
        }
      }
    }
    if ( v7 < 0 )
      goto LABEL_18;
  }
  if ( v24 )
    PiDqActionDataFree(v24);
  if ( P )
    ExFreePoolWithTag(P, 0x58706E50u);
  if ( v15[0] )
    MesHandleFree();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1408ce860  mov     rax, rsp
0x1408ce863  mov     [rax+18h], rbx
0x1408ce867  mov     [rax+8], rcx
0x1408ce86b  push    rsi
0x1408ce86c  push    rdi
0x1408ce86d  push    r12
0x1408ce86f  push    r14
0x1408ce871  push    r15
0x1408ce873  sub     rsp, 60h
0x1408ce877  mov     r14, rcx
0x1408ce87a  xor     edi, edi
0x1408ce87c  mov     esi, edi
0x1408ce87e  mov     [rax-58h], rdi
0x1408ce882  mov     [rax+10h], rdi
0x1408ce886  mov     [rax-2Ah], di
0x1408ce88a  mov     [rax-48h], rdx
0x1408ce88e  mov     [rax-40h], r8d
0x1408ce892  mov     dword ptr [rax-3Ch], 10h
0x1408ce899  mov     [rax-38h], rdi
0x1408ce89d  mov     [rax-30h], edi
0x1408ce8a0  and     r9b, 3
0x1408ce8a4  cmp     r9b, 3
0x1408ce8a8  setz    byte ptr [rax-2Ch]
0x1408ce8ac  mov     [rax-2Bh], dil
0x1408ce8b0  call    PiDqQueryLock
0x1408ce8b5  mov     ebx, [r14+0D8h]
0x1408ce8bc  mov     rcx, r14
0x1408ce8bf  call    PiDqQueryUnlock
0x1408ce8c4  bt      ebx, 5
0x1408ce8c8  jb      short loc_1408CE8DF
0x1408ce8ca  mov     rcx, r14
0x1408ce8cd  call    PiDqQueryGetObjectManager
0x1408ce8d2  mov     rcx, rax; Resource
0x1408ce8d5  mov     rdx, r14
0x1408ce8d8  call    PiDqObjectManagerEnumerateAndRegisterQuery
0x1408ce8dd  mov     esi, eax
0x1408ce8df  test    esi, esi
0x1408ce8e1  js      loc_1408CEAA8
0x1408ce8e7  lea     r9, [rsp+88h+var_58]
0x1408ce8ec  lea     r8, PiDqSerializationWrite
0x1408ce8f3  lea     rdx, PiDqSerializationAlloc
0x1408ce8fa  lea     rcx, [rsp+88h+var_48]
0x1408ce8ff  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x1408ce906  nop     dword ptr [rax+rax+00h]
0x1408ce90b  mov     esi, eax
0x1408ce90d  test    eax, eax
0x1408ce90f  js      loc_1408CEAC6
0x1408ce915  mov     eax, [r14+0D8h]
0x1408ce91c  and     eax, 2
0x1408ce91f  mov     dword ptr [rsp+88h+var_60], eax
0x1408ce923  mov     [rsp+88h+var_68], rdi
0x1408ce928  xor     r9d, r9d
0x1408ce92b  xor     r8d, r8d
0x1408ce92e  lea     rdx, [rsp+88h+var_48]
0x1408ce933  mov     rcx, [rsp+88h+var_58]
0x1408ce938  call    cs:__imp_MesIncrementalHandleReset
0x1408ce93f  nop     dword ptr [rax+rax+00h]
0x1408ce944  mov     esi, eax
0x1408ce946  test    eax, eax
0x1408ce948  js      loc_1408CEAC6
0x1408ce94e  mov     ecx, [rsp+88h+var_3C]
0x1408ce952  mov     rax, [rsp+88h+arg_20]
0x1408ce95a  mov     [rax], ecx
0x1408ce95c  mov     rax, [rsp+88h+arg_28]
0x1408ce964  mov     [rax], edi
0x1408ce966  mov     rcx, r14
0x1408ce969  call    PiDqQueryLock
0x1408ce96e  lea     r12, [r14+0B8h]
0x1408ce975  mov     [rsp+88h+var_50], r12
0x1408ce97a  mov     rax, [r12]
0x1408ce97e  mov     [rsp+88h+arg_8], rax
0x1408ce986  mov     [r12], rdi
0x1408ce98a  mov     rcx, r14
0x1408ce98d  call    PiDqQueryUnlock
0x1408ce992  cmp     [rsp+88h+arg_8], rdi
0x1408ce99a  jz      loc_1408CEA2F
0x1408ce9a0  lea     rax, [rsp+88h+arg_8]
0x1408ce9a8  mov     [rsp+88h+var_60], rax
0x1408ce9ad  mov     dword ptr [rsp+88h+var_68], 1
0x1408ce9b5  lea     r9, off_140E0A510
0x1408ce9bc  lea     r8, off_140004F60
0x1408ce9c3  lea     rdx, aTp3; "TP 3\a"
0x1408ce9ca  mov     rcx, [rsp+88h+var_58]
0x1408ce9cf  call    cs:__imp_NdrMesTypeEncode3
0x1408ce9d6  nop     dword ptr [rax+rax+00h]
0x1408ce9db  jmp     short loc_1408CE9EE
0x1408ce9dd  mov     esi, eax
0x1408ce9df  xor     edi, edi
0x1408ce9e1  mov     r14, [rsp+88h+arg_0]
0x1408ce9e9  mov     r12, [rsp+88h+var_50]
0x1408ce9ee  test    esi, esi
0x1408ce9f0  js      loc_1408CEAA8
0x1408ce9f6  cmp     byte ptr [rsp+88h+var_2A], dil
0x1408ce9fb  jnz     loc_1408CEB5E
0x1408cea01  cmp     [rsp+88h+var_2B], dil
0x1408cea06  jnz     loc_1408CEB24
0x1408cea0c  mov     ecx, [rsp+88h+var_3C]
0x1408cea10  mov     rax, [rsp+88h+arg_20]
0x1408cea18  mov     [rax], ecx
0x1408cea1a  mov     rcx, [rsp+88h+arg_8]; P
0x1408cea22  call    PiDqActionDataFree
0x1408cea27  mov     [rsp+88h+arg_8], rdi
0x1408cea2f  mov     rcx, r14
0x1408cea32  call    PiDqQueryLock
0x1408cea37  lea     rax, [r14+0C0h]
0x1408cea3e  mov     r15, [rax]
0x1408cea41  cmp     r15, rax
0x1408cea44  jz      short loc_1408CEABE
0x1408cea46  cmp     [r15+8], rax
0x1408cea4a  jnz     loc_1408CEB1D
0x1408cea50  mov     rcx, [r15]
0x1408cea53  cmp     [rcx+8], r15
0x1408cea57  jnz     loc_1408CEB1D
0x1408cea5d  mov     [rax], rcx
0x1408cea60  mov     [rcx+8], rax
0x1408cea64  dec     dword ptr [r14+0D0h]
0x1408cea6b  mov     rcx, r14
0x1408cea6e  call    PiDqQueryUnlock
0x1408cea73  lea     rdx, [r14+20h]
0x1408cea77  lea     r9, [rsp+88h+arg_8]
0x1408cea7f  mov     r8, r15
0x1408cea82  mov     rcx, [r14+18h]
0x1408cea86  call    PiDqActionDataCreate
0x1408cea8b  mov     ebx, eax
0x1408cea8d  mov     rcx, r15; P
0x1408cea90  call    PiDqQueryActionQueueEntryFree
0x1408cea95  mov     esi, edi
0x1408cea97  cmp     ebx, 0C0000034h
0x1408cea9d  cmovnz  esi, ebx
0x1408ceaa0  test    esi, esi
0x1408ceaa2  jns     loc_1408CE992
0x1408ceaa8  mov     rax, [rsp+88h+arg_20]
0x1408ceab0  mov     [rax], edi
0x1408ceab2  mov     rax, [rsp+88h+arg_28]
0x1408ceaba  mov     [rax], edi
0x1408ceabc  jmp     short loc_1408CEACA
0x1408ceabe  mov     rcx, r14
0x1408ceac1  call    PiDqQueryUnlock
0x1408ceac6  test    esi, esi
0x1408ceac8  js      short loc_1408CEAA8
0x1408ceaca  mov     rcx, [rsp+88h+arg_8]; P
0x1408cead2  test    rcx, rcx
0x1408cead5  jnz     loc_1408CEB68
0x1408ceadb  mov     rcx, [rsp+88h+P]; P
0x1408ceae0  test    rcx, rcx
0x1408ceae3  jz      short loc_1408CEAEF
0x1408ceae5  mov     edx, 58706E50h; Tag
0x1408ceaea  call    ExFreePoolWithTag
0x1408ceaef  mov     rcx, [rsp+88h+var_58]
0x1408ceaf4  test    rcx, rcx
0x1408ceaf7  jz      short loc_1408CEB05
0x1408ceaf9  call    cs:__imp_MesHandleFree
0x1408ceb00  nop     dword ptr [rax+rax+00h]
0x1408ceb05  mov     eax, esi
0x1408ceb07  mov     rbx, [rsp+88h+arg_10]
0x1408ceb0f  add     rsp, 60h
0x1408ceb13  pop     r15
0x1408ceb15  pop     r14
0x1408ceb17  pop     r12
0x1408ceb19  pop     rdi
0x1408ceb1a  pop     rsi
0x1408ceb1b  retn
0x1408ceb1d  mov     ecx, 3
0x1408ceb22  int     29h; Win8: RtlFailFast(ecx)
0x1408ceb24  mov     rcx, r14
0x1408ceb27  call    PiDqQueryLock
0x1408ceb2c  mov     rax, [rsp+88h+arg_8]
0x1408ceb34  mov     [r12], rax
0x1408ceb38  mov     [rsp+88h+arg_8], rdi
0x1408ceb40  mov     rcx, r14
0x1408ceb43  call    PiDqQueryUnlock
0x1408ceb48  mov     ecx, [rsp+88h+var_30]
0x1408ceb4c  add     ecx, 10h
0x1408ceb4f  mov     rax, [rsp+88h+arg_28]
0x1408ceb57  mov     [rax], ecx
0x1408ceb59  jmp     loc_1408CEAC6
0x1408ceb5e  mov     esi, 0C0000005h
0x1408ceb63  jmp     loc_1408CEAA8
0x1408ceb68  call    PiDqActionDataFree
0x1408ceb6d  jmp     loc_1408CEADB
```
