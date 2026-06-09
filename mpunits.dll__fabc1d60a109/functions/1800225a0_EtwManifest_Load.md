# EtwManifest_Load

- ea: `0x1800225a0`
- end: `0x180022764`
- name: `EtwManifest_Load`
- size: `452`
- prototype: `__int64 __fastcall(wchar_t *String)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180019770`
- `0x1800252b0`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x1800225a0`
- `0x180042dcc`
- `0x180042ecc`
- `0x180043120`
- `0x1800431f0`
- `0x180043d40`
- `0x180043e08`

## import_xrefs

- `msvcrt!malloc` at `0x18002266e`
- `msvcrt!malloc` at `0x18002266e`
- `msvcrt!free` at `0x180022714`
- `msvcrt!free` at `0x18002271d`
- `msvcrt!free` at `0x180022714`
- `msvcrt!free` at `0x18002271d`
- `msvcrt!_wcsdup` at `0x180022683`
- `msvcrt!_wcsdup` at `0x180022683`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800226c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800226c5`
- `tdh!TdhLoadManifest` at `0x1800226a5`
- `tdh!TdhLoadManifest` at `0x1800226a5`
- `tdh!TdhUnloadManifest` at `0x180022754`
- `tdh!TdhUnloadManifest` at `0x180022754`

## string_xrefs

- `0x1800226b7`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall EtwManifest_Load(wchar_t *String, __int64 *a2)
{
  __int64 v2; // rbx
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // r15
  __int64 v8; // rax
  void *v10; // rdi
  wchar_t *v11; // rax
  __int64 v12; // rbx
  HMODULE ModuleHandleA; // rax
  __int128 v14; // [rsp+40h] [rbp-28h] BYREF
  __int128 v15; // [rsp+50h] [rbp-18h]

  v2 = -1;
  v14 = 0;
  v15 = 0;
  do
    ++v2;
  while ( String[v2] );
  if ( !(unsigned int)TryAcquireWrite(&unk_18006DA20) )
    QueueAcquireWrite(&unk_18006DA20);
  if ( (unsigned __int64)qword_18006DA28 < 0xFFFFFFFFFFFFFFFEuLL
    || !(unsigned int)_Once_Invoke(&qword_18006DA28, ManifestTable_Init, 0) )
  {
    v5 = String[v2 - 1];
    v6 = *String;
    v7 = qword_18006DA28;
    *((_QWORD *)&v15 + 1) = String;
    *(_QWORD *)&v15 = v6 + (((v2 << 8) + v5) << 8);
    v8 = HashMap_Find(qword_18006DA28, &v14);
    if ( v8 )
    {
      *a2 = v8;
      ++*(_QWORD *)(v8 + 8);
LABEL_9:
      ReadWriteLock_ReleaseWrite(&unk_18006DA20);
      return 0;
    }
    v10 = malloc(0x20u);
    if ( v10 )
    {
      v11 = _wcsdup(String);
      *((_QWORD *)v10 + 3) = v11;
      if ( v11 )
      {
        *((_QWORD *)v10 + 1) = 1;
        *((_QWORD *)v10 + 2) = v15;
        if ( TdhLoadManifest(v11) )
        {
          v12 = *((_QWORD *)v10 + 3);
          ModuleHandleA = GetModuleHandleA("mpunits.dll");
          Intlstr_FormatString_FormatMessage(ModuleHandleA, 2094, v12);
          MI_ReportErrorDetails_ForCustomError(12, (int)L"ETW Normalizer", 0, 0);
        }
        else
        {
          if ( !(unsigned int)HashMap_Insert(v7, v10) )
          {
            *a2 = (__int64)v10;
            goto LABEL_9;
          }
          TdhUnloadManifest(*((PWSTR *)v10 + 3));
        }
      }
      free(*((void **)v10 + 3));
      free(v10);
    }
  }
  ReadWriteLock_ReleaseWrite(&unk_18006DA20);
  return 27;
}

```

## disassembly

```asm
0x1800225a0  push    rbp
0x1800225a2  push    rbx
0x1800225a3  push    rsi
0x1800225a4  push    rdi
0x1800225a5  push    r12
0x1800225a7  push    r13
0x1800225a9  push    r14
0x1800225ab  push    r15
0x1800225ad  mov     rbp, rsp
0x1800225b0  sub     rsp, 68h
0x1800225b4  xorps   xmm0, xmm0
0x1800225b7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800225bb  movups  [rbp+var_28], xmm0
0x1800225bf  xor     r12d, r12d
0x1800225c2  mov     r14, rdx
0x1800225c5  movups  [rbp+var_18], xmm0
0x1800225c9  mov     rsi, rcx
0x1800225cc  inc     rbx
0x1800225cf  cmp     [rcx+rbx*2], r12w
0x1800225d4  jnz     short loc_1800225CC
0x1800225d6  lea     r13, qword_18006DA20
0x1800225dd  mov     rcx, r13
0x1800225e0  call    TryAcquireWrite
0x1800225e5  test    eax, eax
0x1800225e7  jnz     short loc_1800225F1
0x1800225e9  mov     rcx, r13
0x1800225ec  call    QueueAcquireWrite
0x1800225f1  mov     rax, cs:qword_18006DA28
0x1800225f8  nop
0x1800225f9  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x1800225fd  jb      short loc_18002261D
0x1800225ff  xor     r8d, r8d
0x180022602  lea     rdx, ManifestTable_Init
0x180022609  lea     rcx, qword_18006DA28
0x180022610  call    __Once_Invoke
0x180022615  test    eax, eax
0x180022617  jnz     loc_180022723
0x18002261d  movzx   edx, word ptr [rsi+rbx*2-2]
0x180022622  movzx   eax, word ptr [rsi]
0x180022625  mov     r15, cs:qword_18006DA28
0x18002262c  shl     rbx, 8
0x180022630  mov     rcx, r15
0x180022633  add     rdx, rbx
0x180022636  mov     qword ptr [rbp+var_18+8], rsi
0x18002263a  shl     rdx, 8
0x18002263e  add     rdx, rax
0x180022641  mov     qword ptr [rbp+var_18], rdx
0x180022645  lea     rdx, [rbp+var_28]
0x180022649  call    HashMap_Find
0x18002264e  test    rax, rax
0x180022651  jz      short loc_180022669
0x180022653  mov     [r14], rax
0x180022656  inc     qword ptr [rax+8]
0x18002265a  mov     rcx, r13
0x18002265d  call    ReadWriteLock_ReleaseWrite
0x180022662  xor     eax, eax
0x180022664  jmp     loc_180022730
0x180022669  mov     ecx, 20h ; ' '; Size
0x18002266e  call    cs:__imp_malloc
0x180022674  mov     rdi, rax
0x180022677  test    rax, rax
0x18002267a  jz      loc_180022723
0x180022680  mov     rcx, rsi; String
0x180022683  call    cs:__imp__wcsdup
0x180022689  mov     [rdi+18h], rax
0x18002268d  test    rax, rax
0x180022690  jz      short loc_180022710
0x180022692  mov     qword ptr [rdi+8], 1
0x18002269a  mov     rcx, qword ptr [rbp+var_18]
0x18002269e  mov     [rdi+10h], rcx
0x1800226a2  mov     rcx, rax; Manifest
0x1800226a5  call    cs:__imp_TdhLoadManifest
0x1800226ab  test    eax, eax
0x1800226ad  jz      loc_180022741
0x1800226b3  mov     rbx, [rdi+18h]
0x1800226b7  lea     rcx, ModuleName; "mpunits.dll"
0x1800226be  xorps   xmm0, xmm0
0x1800226c1  movups  [rbp+var_38], xmm0
0x1800226c5  call    cs:__imp_GetModuleHandleA
0x1800226cb  mov     r8, rbx
0x1800226ce  mov     edx, 82Eh
0x1800226d3  mov     rcx, rax
0x1800226d6  call    _Intlstr_FormatString_FormatMessage
0x1800226db  mov     qword ptr [rbp+var_38], rax
0x1800226df  lea     r9, [rbp+var_38]
0x1800226e3  mov     byte ptr [rbp+var_38+8], 1
0x1800226e7  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x1800226ee  movaps  xmm0, [rbp+var_38]
0x1800226f2  mov     r8d, 6
0x1800226f8  mov     [rsp+68h+var_40], r12; __int64
0x1800226fd  movdqa  [rbp+var_38], xmm0
0x180022702  mov     [rsp+68h+var_48], r12; __int64
0x180022707  lea     ecx, [r8+6]; int
0x18002270b  call    MI_ReportErrorDetails_ForCustomError
0x180022710  mov     rcx, [rdi+18h]; Block
0x180022714  call    cs:__imp_free
0x18002271a  mov     rcx, rdi; Block
0x18002271d  call    cs:__imp_free
0x180022723  mov     rcx, r13
0x180022726  call    ReadWriteLock_ReleaseWrite
0x18002272b  mov     eax, 1Bh
0x180022730  add     rsp, 68h
0x180022734  pop     r15
0x180022736  pop     r14
0x180022738  pop     r13
0x18002273a  pop     r12
0x18002273c  pop     rdi
0x18002273d  pop     rsi
0x18002273e  pop     rbx
0x18002273f  pop     rbp
0x180022740  retn
0x180022741  mov     rdx, rdi
0x180022744  mov     rcx, r15
0x180022747  call    HashMap_Insert
0x18002274c  test    eax, eax
0x18002274e  jz      short loc_18002275C
0x180022750  mov     rcx, [rdi+18h]; Manifest
0x180022754  call    cs:__imp_TdhUnloadManifest
0x18002275a  jmp     short loc_180022710
0x18002275c  mov     [r14], rdi
0x18002275f  jmp     loc_18002265A
```
