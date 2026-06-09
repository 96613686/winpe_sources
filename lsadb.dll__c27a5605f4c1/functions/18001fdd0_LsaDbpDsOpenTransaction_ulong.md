# LsaDbpDsOpenTransaction(ulong)

- ea: `0x18001fdd0`
- end: `0x18001ff00`
- name: `?LsaDbpDsOpenTransaction@@YAJK@Z`
- size: `304`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000fd18`
- `0x18000fd40`
- `0x180011d30`
- `0x180015554`
- `0x180015664`
- `0x18001fdd0`

## import_xrefs

- `NTDSA!THCreate` at `0x18001fe34`
- `NTDSA!THCreate` at `0x18001fe34`
- `NTDSA!SampExistsDsTransaction` at `0x18001fe7a`
- `NTDSA!SampExistsDsTransaction` at `0x18001fe7a`
- `NTDSA!THQuery` at `0x18001fe63`
- `NTDSA!THQuery` at `0x18001fe63`
- `NTDSA!SampSetDsa` at `0x18001fec6`
- `NTDSA!SampSetDsa` at `0x18001fec6`
- `NTDSA!DirTransactControl` at `0x18001fe89`
- `NTDSA!DirTransactControl` at `0x18001fe99`
- `NTDSA!DirTransactControl` at `0x18001fe89`
- `NTDSA!DirTransactControl` at `0x18001fe99`
- `NTDSA!THRestore` at `0x18001fe4b`
- `NTDSA!THRestore` at `0x18001fe4b`
- `NTDSA!THSave` at `0x18001fe25`
- `NTDSA!THSave` at `0x18001fe25`

## pseudocode

```c
__int64 __fastcall LsaDbpDsOpenTransaction(int a1)
{
  struct _LSADS_PER_THREAD_INFO *ThreadInfo; // rax
  struct _LSADS_PER_THREAD_INFO *v3; // rbx
  int v4; // edi
  unsigned int v5; // eax
  void *v6; // rcx

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_49c8527826843b97b1b25aea330fd00e_Traceguids);
  if ( (a1 & 0x4000000) == 0 )
  {
    ThreadInfo = LsaDbpCreateThreadInfo();
    v3 = ThreadInfo;
    if ( !ThreadInfo )
    {
      v4 = -1073741670;
      goto LABEL_19;
    }
    if ( !*((_DWORD *)ThreadInfo + 2) )
    {
      *((_QWORD *)ThreadInfo + 4) = THSave();
      v5 = THCreate(4);
      v4 = LsaDbpDsMapDsReturnToStatus(v5);
      if ( v4 < 0 )
      {
        THRestore(*((_QWORD *)v3 + 4));
        *((_QWORD *)v3 + 4) = 0;
        LsaDbpClearThreadInfo();
        goto LABEL_19;
      }
    }
    ++*((_DWORD *)v3 + 2);
    if ( !(unsigned int)THQuery() )
    {
      v4 = -1073741801;
      goto LABEL_19;
    }
    if ( !*((_DWORD *)v3 + 3) )
    {
      if ( (unsigned int)SampExistsDsTransaction() )
      {
        DirTransactControl(3);
        ++*((_DWORD *)v3 + 4);
      }
      else
      {
        DirTransactControl(2);
      }
      v6 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_49c8527826843b97b1b25aea330fd00e_Traceguids);
    }
    ++*((_DWORD *)v3 + 3);
    LOBYTE(v6) = 1;
    SampSetDsa(v6);
  }
  v4 = 0;
LABEL_19:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_49c8527826843b97b1b25aea330fd00e_Traceguids,
      (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001fdd0  mov     [rsp+arg_0], rbx
0x18001fdd5  push    rdi
0x18001fdd6  sub     rsp, 20h
0x18001fdda  mov     ebx, ecx
0x18001fddc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fde3  test    byte ptr [rcx+1Ch], 1
0x18001fde7  jz      short loc_18001FDFE
0x18001fde9  mov     rcx, [rcx+10h]
0x18001fded  lea     r8, WPP_49c8527826843b97b1b25aea330fd00e_Traceguids
0x18001fdf4  mov     edx, 16h
0x18001fdf9  call    WPP_SF_
0x18001fdfe  bt      ebx, 1Ah
0x18001fe02  jb      loc_18001FECC
0x18001fe08  call    ?LsaDbpCreateThreadInfo@@YAPEAU_LSADS_PER_THREAD_INFO@@XZ; LsaDbpCreateThreadInfo(void)
0x18001fe0d  mov     rbx, rax
0x18001fe10  test    rax, rax
0x18001fe13  jnz     short loc_18001FE1F
0x18001fe15  mov     edi, 0C000009Ah
0x18001fe1a  jmp     loc_18001FECE
0x18001fe1f  cmp     dword ptr [rax+8], 0
0x18001fe23  jnz     short loc_18001FE60
0x18001fe25  call    cs:__imp_THSave
0x18001fe2b  mov     ecx, 4
0x18001fe30  mov     [rbx+20h], rax
0x18001fe34  call    cs:__imp_THCreate
0x18001fe3a  mov     ecx, eax; unsigned int
0x18001fe3c  call    ?LsaDbpDsMapDsReturnToStatus@@YAJK@Z; LsaDbpDsMapDsReturnToStatus(ulong)
0x18001fe41  mov     edi, eax
0x18001fe43  test    eax, eax
0x18001fe45  jns     short loc_18001FE60
0x18001fe47  mov     rcx, [rbx+20h]
0x18001fe4b  call    cs:__imp_THRestore
0x18001fe51  mov     qword ptr [rbx+20h], 0
0x18001fe59  call    ?LsaDbpClearThreadInfo@@YAXXZ; LsaDbpClearThreadInfo(void)
0x18001fe5e  jmp     short loc_18001FECE
0x18001fe60  inc     dword ptr [rbx+8]
0x18001fe63  call    cs:__imp_THQuery
0x18001fe69  test    eax, eax
0x18001fe6b  jnz     short loc_18001FE74
0x18001fe6d  mov     edi, 0C0000017h
0x18001fe72  jmp     short loc_18001FECE
0x18001fe74  cmp     dword ptr [rbx+0Ch], 0
0x18001fe78  jnz     short loc_18001FEC1
0x18001fe7a  call    cs:__imp_SampExistsDsTransaction
0x18001fe80  test    eax, eax
0x18001fe82  jz      short loc_18001FE94
0x18001fe84  mov     ecx, 3
0x18001fe89  call    cs:__imp_DirTransactControl
0x18001fe8f  inc     dword ptr [rbx+10h]
0x18001fe92  jmp     short loc_18001FE9F
0x18001fe94  mov     ecx, 2
0x18001fe99  call    cs:__imp_DirTransactControl
0x18001fe9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fea6  test    byte ptr [rcx+1Ch], 1
0x18001feaa  jz      short loc_18001FEC1
0x18001feac  mov     rcx, [rcx+10h]
0x18001feb0  lea     r8, WPP_49c8527826843b97b1b25aea330fd00e_Traceguids
0x18001feb7  mov     edx, 17h
0x18001febc  call    WPP_SF_
0x18001fec1  inc     dword ptr [rbx+0Ch]
0x18001fec4  mov     cl, 1
0x18001fec6  call    cs:__imp_SampSetDsa
0x18001fecc  xor     edi, edi
0x18001fece  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fed5  test    byte ptr [rcx+1Ch], 1
0x18001fed9  jz      short loc_18001FEF3
0x18001fedb  mov     rcx, [rcx+10h]
0x18001fedf  lea     r8, WPP_49c8527826843b97b1b25aea330fd00e_Traceguids
0x18001fee6  mov     edx, 18h
0x18001feeb  mov     r9d, edi
0x18001feee  call    WPP_SF_d
0x18001fef3  mov     rbx, [rsp+28h+arg_0]
0x18001fef8  mov     eax, edi
0x18001fefa  add     rsp, 20h
0x18001fefe  pop     rdi
0x18001feff  retn
```
