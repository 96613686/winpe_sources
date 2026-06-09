# IP_MODULE::GetIpRecord(STTABLE *,STBUFF *,STBUFF *,IP_RECORD * *)

- ea: `0x180005168`
- end: `0x1800053a8`
- name: `?GetIpRecord@IP_MODULE@@CAJPEAVSTTABLE@@PEAVSTBUFF@@1PEAPEAVIP_RECORD@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(struct STTABLE *this, struct STBUFF *, struct STBUFF *, struct IP_RECORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800047a4`

## callees

- `0x180001008`
- `0x180001948`
- `0x180001a2c`
- `0x180005168`
- `0x1800053b0`
- `0x180005e7c`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005287`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000527d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000527d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000529e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000529e`
- `iisutil!PuDbgPrint` at `0x180005345`
- `iisutil!PuDbgPrint` at `0x180005345`

## string_xrefs

- `0x18000530b`: `servercommon\inetsrv\iis\iisrearc\iis70\dynamiciprestriction\dipmodule.cpp`

## pseudocode

```c
__int64 __fastcall IP_MODULE::GetIpRecord(
        struct STTABLE *this,
        struct STBUFF *a2,
        struct STBUFF *a3,
        struct IP_RECORD **a4)
{
  signed int Item; // ebx
  struct STTABLE_ITEM *v9; // rdi
  int v10; // edx
  int v11; // edx
  __int64 v12; // r8
  _BYTE *v13; // rdx
  signed int LastError; // eax
  __int64 v15; // r8
  _BYTE *v16; // rdx
  int v17; // eax
  struct STTABLE_ITEM *v19[9]; // [rsp+30h] [rbp-48h] BYREF

  v19[0] = 0;
  *a4 = 0;
  Item = STTABLE::GetItem(this, a3, v19);
  if ( (int)(Item + 0x80000000) < 0 || Item == -2147024894 )
  {
    v9 = v19[0];
    if ( v19[0] )
    {
LABEL_19:
      *a4 = v9;
      return (unsigned int)Item;
    }
    v9 = (struct STTABLE_ITEM *)operator new(0x128u);
    if ( !v9 )
      return (unsigned int)-2147024882;
    *((_DWORD *)v9 + 6) = 1;
    *(_QWORD *)v9 = &STTABLE_ITEM::`vftable';
    STBUFF::STBUFF((struct STTABLE_ITEM *)((char *)v9 + 32), v10);
    *((_QWORD *)v9 + 2) = (char *)v9 + 8;
    *((_QWORD *)v9 + 1) = (char *)v9 + 8;
    *(_QWORD *)v9 = &IP_RECORD::`vftable';
    STBUFF::STBUFF((struct STTABLE_ITEM *)((char *)v9 + 128), v11);
    *((_QWORD *)v9 + 28) = 0;
    *((_DWORD *)v9 + 72) = 0;
    *(_BYTE *)(*((unsigned int *)a2 + 4) + *((_QWORD *)a2 + 1)) = 0;
    v12 = -1;
    *(_BYTE *)((unsigned int)(*((_DWORD *)a2 + 4) + 1) + *((_QWORD *)a2 + 1)) = 0;
    v13 = (_BYTE *)*((_QWORD *)a2 + 1);
    do
      ++v12;
    while ( v13[v12] );
    Item = STBUFF::AppendData((struct STTABLE_ITEM *)((char *)v9 + 128), v13, v12, 0);
    if ( Item >= 0 )
    {
      if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)v9 + 248), 0x64u) )
      {
        *((_QWORD *)v9 + 29) = GetTickCount64();
        *((_DWORD *)v9 + 72) = 1;
        LODWORD(v15) = *((_DWORD *)a3 + 4);
        v16 = (_BYTE *)*((_QWORD *)a3 + 1);
        if ( (_DWORD)v15 == -1 )
        {
          v15 = -1;
          do
            ++v15;
          while ( v16[v15] );
        }
        Item = STBUFF::AppendData((struct STTABLE_ITEM *)((char *)v9 + 32), v16, v15, 0);
      }
      else
      {
        LastError = GetLastError();
        Item = LastError;
        if ( LastError > 0 )
          Item = (unsigned __int16)LastError | 0x80070000;
      }
      if ( Item >= 0 )
      {
        v17 = STTABLE::Insert(this, v9);
        Item = v17;
        if ( v17 >= 0 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            *(_BYTE *)(*((unsigned int *)a2 + 4) + *((_QWORD *)a2 + 1)) = 0;
            *(_BYTE *)((unsigned int)(*((_DWORD *)a2 + 4) + 1) + *((_QWORD *)a2 + 1)) = 0;
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\dynamiciprestriction\\dipmodule.cpp",
              1524,
              "IP_MODULE::GetIpRecord",
              "Added record for client %s.\n",
              *((const char **)a2 + 1));
          }
          goto LABEL_19;
        }
        if ( v17 == -2147024713 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 6, 0xFFFFFFFF) == 1 )
            (**(void (__fastcall ***)(struct STTABLE_ITEM *, __int64))v9)(v9, 1);
          Item = STTABLE::GetItem(this, a3, v19);
          if ( Item >= 0 )
          {
            v9 = v19[0];
            goto LABEL_19;
          }
        }
      }
    }
  }
  return (unsigned int)Item;
}

```

## disassembly

```asm
0x180005168  push    rbx
0x18000516a  push    rbp
0x18000516b  push    rsi
0x18000516c  push    rdi
0x18000516d  push    r14
0x18000516f  push    r15
0x180005171  sub     rsp, 48h
0x180005175  mov     rbp, r8
0x180005178  mov     [rsp+78h+var_48], 0
0x180005181  mov     rsi, rdx
0x180005184  mov     qword ptr [r9], 0
0x18000518b  mov     rdx, rbp; struct STBUFF *
0x18000518e  lea     r8, [rsp+78h+var_48]; struct STTABLE_ITEM **
0x180005193  mov     r15, r9
0x180005196  mov     r14, rcx
0x180005199  call    ?GetItem@STTABLE@@QEAAJPEAVSTBUFF@@PEAPEAVSTTABLE_ITEM@@@Z; STTABLE::GetItem(STBUFF *,STTABLE_ITEM * *)
0x18000519e  mov     ebx, eax
0x1800051a0  mov     eax, 80000000h
0x1800051a5  lea     r9d, [rbx+rax]
0x1800051a9  test    eax, r9d
0x1800051ac  jnz     short loc_1800051BA
0x1800051ae  cmp     ebx, 80070002h
0x1800051b4  jnz     loc_18000534E
0x1800051ba  mov     rdi, [rsp+78h+var_48]
0x1800051bf  test    rdi, rdi
0x1800051c2  jnz     loc_18000534B
0x1800051c8  mov     ecx, 128h; Size
0x1800051cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800051d2  mov     rdi, rax
0x1800051d5  test    rax, rax
0x1800051d8  jz      loc_1800053A1
0x1800051de  lea     rax, ??_7STTABLE_ITEM@@6B@; const STTABLE_ITEM::`vftable'
0x1800051e5  mov     dword ptr [rdi+18h], 1
0x1800051ec  lea     rcx, [rdi+20h]; this
0x1800051f0  mov     [rdi], rax
0x1800051f3  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x1800051f8  lea     rcx, [rdi+8]
0x1800051fc  mov     [rcx+8], rcx
0x180005200  lea     rax, ??_7IP_RECORD@@6B@; const IP_RECORD::`vftable'
0x180005207  mov     [rcx], rcx
0x18000520a  lea     rcx, [rdi+80h]; this
0x180005211  mov     [rdi], rax
0x180005214  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180005219  mov     qword ptr [rdi+0E0h], 0
0x180005224  mov     dword ptr [rdi+120h], 0
0x18000522e  mov     ecx, [rsi+10h]
0x180005231  mov     rax, [rsi+8]
0x180005235  mov     byte ptr [rcx+rax], 0
0x180005239  mov     ecx, [rsi+10h]
0x18000523c  mov     rax, [rsi+8]
0x180005240  inc     ecx
0x180005242  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005246  mov     byte ptr [rcx+rax], 0
0x18000524a  mov     rdx, [rsi+8]; void *
0x18000524e  inc     r8; unsigned int
0x180005251  cmp     byte ptr [rdx+r8], 0
0x180005256  jnz     short loc_18000524E
0x180005258  lea     rcx, [rdi+80h]; this
0x18000525f  xor     r9d, r9d; unsigned int
0x180005262  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x180005267  mov     ebx, eax
0x180005269  test    eax, eax
0x18000526b  js      loc_18000534E
0x180005271  lea     rcx, [rdi+0F8h]; lpCriticalSection
0x180005278  mov     edx, 64h ; 'd'; dwSpinCount
0x18000527d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180005283  test    eax, eax
0x180005285  jnz     short loc_18000529E
0x180005287  call    cs:__imp_GetLastError
0x18000528d  mov     ebx, eax
0x18000528f  test    eax, eax
0x180005291  jle     short loc_1800052DF
0x180005293  movzx   ebx, ax
0x180005296  or      ebx, 80070000h
0x18000529c  jmp     short loc_1800052DF
0x18000529e  call    cs:__imp_GetTickCount64
0x1800052a4  mov     [rdi+0E8h], rax
0x1800052ab  mov     dword ptr [rdi+120h], 1
0x1800052b5  mov     r8d, [rbp+10h]
0x1800052b9  mov     rdx, [rbp+8]; void *
0x1800052bd  cmp     r8d, 0FFFFFFFFh
0x1800052c1  jnz     short loc_1800052D1
0x1800052c3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800052c7  inc     r8; unsigned int
0x1800052ca  cmp     byte ptr [rdx+r8], 0
0x1800052cf  jnz     short loc_1800052C7
0x1800052d1  lea     rcx, [rdi+20h]; this
0x1800052d5  xor     r9d, r9d; unsigned int
0x1800052d8  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x1800052dd  mov     ebx, eax
0x1800052df  test    ebx, ebx
0x1800052e1  js      short loc_18000534E
0x1800052e3  mov     rdx, rdi; struct STTABLE_ITEM *
0x1800052e6  mov     rcx, r14; this
0x1800052e9  call    ?Insert@STTABLE@@QEAAJPEAVSTTABLE_ITEM@@@Z; STTABLE::Insert(STTABLE_ITEM *)
0x1800052ee  mov     ebx, eax
0x1800052f0  test    eax, eax
0x1800052f2  js      short loc_18000535D
0x1800052f4  test    byte ptr cs:g_dwDebugFlags, 3
0x1800052fb  jz      short loc_18000534B
0x1800052fd  mov     ecx, [rsi+10h]
0x180005300  lea     r9, aIpModuleGetipr; "IP_MODULE::GetIpRecord"
0x180005307  mov     rax, [rsi+8]
0x18000530b  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005312  mov     r8d, 5F4h
0x180005318  mov     byte ptr [rcx+rax], 0
0x18000531c  mov     ecx, [rsi+10h]
0x18000531f  mov     rax, [rsi+8]
0x180005323  inc     ecx
0x180005325  mov     byte ptr [rcx+rax], 0
0x180005329  mov     rax, [rsi+8]
0x18000532d  mov     rcx, cs:g_pDebug
0x180005334  mov     [rsp+78h+var_50], rax
0x180005339  lea     rax, aAddedRecordFor; "Added record for client %s.\n"
0x180005340  mov     [rsp+78h+var_58], rax
0x180005345  call    cs:__imp_PuDbgPrint
0x18000534b  mov     [r15], rdi
0x18000534e  mov     eax, ebx
0x180005350  add     rsp, 48h
0x180005354  pop     r15
0x180005356  pop     r14
0x180005358  pop     rdi
0x180005359  pop     rsi
0x18000535a  pop     rbp
0x18000535b  pop     rbx
0x18000535c  retn
0x18000535d  cmp     eax, 800700B7h
0x180005362  jnz     short loc_18000534E
0x180005364  or      eax, 0FFFFFFFFh
0x180005367  lock xadd [rdi+18h], eax
0x18000536c  cmp     eax, 1
0x18000536f  jnz     short loc_180005384
0x180005371  mov     rax, [rdi]
0x180005374  mov     edx, 1
0x180005379  mov     rcx, rdi
0x18000537c  mov     rax, [rax]
0x18000537f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005384  lea     r8, [rsp+78h+var_48]; struct STTABLE_ITEM **
0x180005389  mov     rdx, rbp; struct STBUFF *
0x18000538c  mov     rcx, r14; this
0x18000538f  call    ?GetItem@STTABLE@@QEAAJPEAVSTBUFF@@PEAPEAVSTTABLE_ITEM@@@Z; STTABLE::GetItem(STBUFF *,STTABLE_ITEM * *)
0x180005394  mov     ebx, eax
0x180005396  test    eax, eax
0x180005398  js      short loc_18000534E
0x18000539a  mov     rdi, [rsp+78h+var_48]
0x18000539f  jmp     short loc_18000534B
0x1800053a1  mov     ebx, 8007000Eh
0x1800053a6  jmp     short loc_18000534E
```
