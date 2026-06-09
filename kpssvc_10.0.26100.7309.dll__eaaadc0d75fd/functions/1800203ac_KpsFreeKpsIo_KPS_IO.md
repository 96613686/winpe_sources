# KpsFreeKpsIo(_KPS_IO *)

- ea: `0x1800203ac`
- end: `0x180020607`
- name: `?KpsFreeKpsIo@@YAXPEAU_KPS_IO@@@Z`
- size: `603`
- prototype: `void __fastcall(struct _KPS_IO *lpMem)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001e520`
- `0x1800210f4`
- `0x180021b10`
- `0x180024be0`

## callees

- `0x18001ae0c`
- `0x1800203ac`
- `0x180026d9c`
- `0x1800288c4`
- `0x18003012c`

## import_xrefs

- `WS2_32!FreeAddrInfoW` at `0x180020533`
- `WS2_32!FreeAddrInfoW` at `0x180020533`
- `WS2_32!__imp_closesocket` at `0x18002054c`
- `WS2_32!__imp_closesocket` at `0x18002054c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180020564`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180020564`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002057c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002057c`
- `ntdll!RtlLeaveCriticalSection` at `0x180020409`
- `ntdll!RtlLeaveCriticalSection` at `0x180020474`
- `ntdll!RtlLeaveCriticalSection` at `0x180020409`
- `ntdll!RtlLeaveCriticalSection` at `0x180020474`
- `ntdll!RtlEnterCriticalSection` at `0x18002042b`
- `ntdll!RtlEnterCriticalSection` at `0x18002042b`
- `ntdll!RtlFreeUnicodeString` at `0x1800204b2`
- `ntdll!RtlFreeUnicodeString` at `0x1800204f5`
- `ntdll!RtlFreeUnicodeString` at `0x180020508`
- `ntdll!RtlFreeUnicodeString` at `0x18002051b`
- `ntdll!RtlFreeUnicodeString` at `0x1800204b2`
- `ntdll!RtlFreeUnicodeString` at `0x1800204f5`
- `ntdll!RtlFreeUnicodeString` at `0x180020508`
- `ntdll!RtlFreeUnicodeString` at `0x18002051b`
- `ntdll!RtlDeleteCriticalSection` at `0x180020418`
- `ntdll!RtlDeleteCriticalSection` at `0x180020418`

## pseudocode

```c
void __fastcall KpsFreeKpsIo(struct _KPS_IO *lpMem)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rax
  __int64 v4; // rdx
  _QWORD *v5; // rcx
  void *v6; // rdx
  void *v7; // rdx
  int v8; // eax
  unsigned int v9; // ecx
  struct addrinfoW *v10; // rcx
  SOCKET v11; // rcx
  struct _TP_IO *v12; // rcx
  struct _TP_WAIT *v13; // rcx
  void *v14; // rdx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, lpMem);
    v2 = WPP_GLOBAL_Control;
  }
  if ( lpMem )
  {
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)lpMem + 288));
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)lpMem + 288));
    RtlEnterCriticalSection(&stru_18003AC20);
    v3 = (_QWORD *)((char *)lpMem + 40);
    v4 = *((_QWORD *)lpMem + 5);
    if ( v4 && *((_QWORD *)lpMem + 6) )
    {
      if ( *(_QWORD **)(v4 + 8) != v3 || (v5 = (_QWORD *)*((_QWORD *)lpMem + 6), (_QWORD *)*v5 != v3) )
        __fastfail(3u);
      *v5 = v4;
      *(_QWORD *)(v4 + 8) = v5;
      *v3 = 0;
      *((_QWORD *)lpMem + 6) = 0;
    }
    RtlLeaveCriticalSection(&stru_18003AC20);
    KpsFreeMem(*((void **)lpMem + 7));
    KpsFreeMem(*((void **)lpMem + 9));
    KpsFreeMem(*((void **)lpMem + 11));
    v6 = (void *)*((_QWORD *)lpMem + 13);
    if ( v6 )
      KpsDerFree(0x28u, v6);
    RtlFreeUnicodeString((PUNICODE_STRING)lpMem + 7);
    v7 = (void *)*((_QWORD *)lpMem + 17);
    if ( !v7 )
      goto LABEL_19;
    v8 = *((_DWORD *)lpMem + 33);
    if ( v8 == 1 )
    {
      v9 = 78;
    }
    else
    {
      if ( v8 != 2 )
      {
LABEL_19:
        RtlFreeUnicodeString((PUNICODE_STRING)((char *)lpMem + 152));
        RtlFreeUnicodeString((PUNICODE_STRING)((char *)lpMem + 168));
        RtlFreeUnicodeString((PUNICODE_STRING)((char *)lpMem + 184));
        v10 = (struct addrinfoW *)*((_QWORD *)lpMem + 25);
        if ( v10 )
          FreeAddrInfoW(v10);
        v11 = *((_QWORD *)lpMem + 27);
        if ( v11 != -1 )
          closesocket(v11);
        v12 = (struct _TP_IO *)*((_QWORD *)lpMem + 28);
        if ( v12 )
          CloseThreadpoolIo(v12);
        v13 = (struct _TP_WAIT *)*((_QWORD *)lpMem + 41);
        if ( v13 )
          CloseThreadpoolWait(v13);
        v14 = (void *)*((_QWORD *)lpMem + 31);
        if ( v14 && *((_DWORD *)lpMem + 61) == 1 )
          KpsDerFree(6u, v14);
        KpsFreeMem(*((void **)lpMem + 32));
        KpsFreeMem(*((void **)lpMem + 34));
        KpsFreeMem(lpMem);
        _InterlockedDecrement64(&qword_18003AC58);
        v2 = WPP_GLOBAL_Control;
        goto LABEL_31;
      }
      v9 = 79;
    }
    KpsDerFree(v9, v7);
    goto LABEL_19;
  }
LABEL_31:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_(v2[2], 11, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids);
}

```

## disassembly

```asm
0x1800203ac  mov     [rsp+arg_0], rbx
0x1800203b1  mov     [rsp+arg_8], rbp
0x1800203b6  push    rdi
0x1800203b7  sub     rsp, 20h
0x1800203bb  mov     rdi, rcx
0x1800203be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203c5  lea     rbp, WPP_GLOBAL_Control
0x1800203cc  cmp     rcx, rbp
0x1800203cf  jz      short loc_1800203F6
0x1800203d1  test    byte ptr [rcx+1Ch], 20h
0x1800203d5  jz      short loc_1800203F6
0x1800203d7  mov     rcx, [rcx+10h]
0x1800203db  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x1800203e2  mov     edx, 0Ah
0x1800203e7  mov     r9, rdi
0x1800203ea  call    WPP_SF_q
0x1800203ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203f6  test    rdi, rdi
0x1800203f9  jz      loc_1800205D6
0x1800203ff  lea     rbx, [rdi+120h]
0x180020406  mov     rcx, rbx; CriticalSection
0x180020409  call    cs:__imp_RtlLeaveCriticalSection
0x180020410  nop     dword ptr [rax+rax+00h]
0x180020415  mov     rcx, rbx; CriticalSection
0x180020418  call    cs:__imp_RtlDeleteCriticalSection
0x18002041f  nop     dword ptr [rax+rax+00h]
0x180020424  lea     rcx, stru_18003AC20; CriticalSection
0x18002042b  call    cs:__imp_RtlEnterCriticalSection
0x180020432  nop     dword ptr [rax+rax+00h]
0x180020437  lea     rax, [rdi+28h]
0x18002043b  mov     rdx, [rax]
0x18002043e  test    rdx, rdx
0x180020441  jz      short loc_18002046D
0x180020443  cmp     qword ptr [rdi+30h], 0
0x180020448  jz      short loc_18002046D
0x18002044a  cmp     [rdx+8], rax
0x18002044e  jnz     loc_1800204DA
0x180020454  mov     rcx, [rax+8]
0x180020458  cmp     [rcx], rax
0x18002045b  jnz     short loc_1800204DA
0x18002045d  mov     [rcx], rdx
0x180020460  mov     [rdx+8], rcx
0x180020464  and     qword ptr [rax], 0
0x180020468  and     qword ptr [rdi+30h], 0
0x18002046d  lea     rcx, stru_18003AC20; CriticalSection
0x180020474  call    cs:__imp_RtlLeaveCriticalSection
0x18002047b  nop     dword ptr [rax+rax+00h]
0x180020480  mov     rcx, [rdi+38h]; lpMem
0x180020484  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x180020489  mov     rcx, [rdi+48h]; lpMem
0x18002048d  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x180020492  mov     rcx, [rdi+58h]; lpMem
0x180020496  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x18002049b  mov     rdx, [rdi+68h]; void *
0x18002049f  test    rdx, rdx
0x1800204a2  jz      short loc_1800204AE
0x1800204a4  mov     ecx, 28h ; '('; unsigned int
0x1800204a9  call    ?KpsDerFree@@YAXKPEAX@Z; KpsDerFree(ulong,void *)
0x1800204ae  lea     rcx, [rdi+70h]; UnicodeString
0x1800204b2  call    cs:__imp_RtlFreeUnicodeString
0x1800204b9  nop     dword ptr [rax+rax+00h]
0x1800204be  mov     rdx, [rdi+88h]; void *
0x1800204c5  test    rdx, rdx
0x1800204c8  jz      short loc_1800204EE
0x1800204ca  mov     eax, [rdi+84h]
0x1800204d0  cmp     eax, 1
0x1800204d3  jnz     short loc_1800204E1
0x1800204d5  lea     ecx, [rax+4Dh]
0x1800204d8  jmp     short loc_1800204E9
0x1800204da  mov     ecx, 3
0x1800204df  int     29h; Win8: RtlFailFast(ecx)
0x1800204e1  cmp     eax, 2
0x1800204e4  jnz     short loc_1800204EE
0x1800204e6  lea     ecx, [rax+4Dh]; unsigned int
0x1800204e9  call    ?KpsDerFree@@YAXKPEAX@Z; KpsDerFree(ulong,void *)
0x1800204ee  lea     rcx, [rdi+98h]; UnicodeString
0x1800204f5  call    cs:__imp_RtlFreeUnicodeString
0x1800204fc  nop     dword ptr [rax+rax+00h]
0x180020501  lea     rcx, [rdi+0A8h]; UnicodeString
0x180020508  call    cs:__imp_RtlFreeUnicodeString
0x18002050f  nop     dword ptr [rax+rax+00h]
0x180020514  lea     rcx, [rdi+0B8h]; UnicodeString
0x18002051b  call    cs:__imp_RtlFreeUnicodeString
0x180020522  nop     dword ptr [rax+rax+00h]
0x180020527  mov     rcx, [rdi+0C8h]; pAddrInfo
0x18002052e  test    rcx, rcx
0x180020531  jz      short loc_18002053F
0x180020533  call    cs:__imp_FreeAddrInfoW
0x18002053a  nop     dword ptr [rax+rax+00h]
0x18002053f  mov     rcx, [rdi+0D8h]; s
0x180020546  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002054a  jz      short loc_180020558
0x18002054c  call    cs:__imp_closesocket
0x180020553  nop     dword ptr [rax+rax+00h]
0x180020558  mov     rcx, [rdi+0E0h]; pio
0x18002055f  test    rcx, rcx
0x180020562  jz      short loc_180020570
0x180020564  call    cs:__imp_CloseThreadpoolIo
0x18002056b  nop     dword ptr [rax+rax+00h]
0x180020570  mov     rcx, [rdi+148h]; pwa
0x180020577  test    rcx, rcx
0x18002057a  jz      short loc_180020588
0x18002057c  call    cs:__imp_CloseThreadpoolWait
0x180020583  nop     dword ptr [rax+rax+00h]
0x180020588  mov     rdx, [rdi+0F8h]; void *
0x18002058f  test    rdx, rdx
0x180020592  jz      short loc_1800205A7
0x180020594  cmp     dword ptr [rdi+0F4h], 1
0x18002059b  jnz     short loc_1800205A7
0x18002059d  mov     ecx, 6; unsigned int
0x1800205a2  call    ?KpsDerFree@@YAXKPEAX@Z; KpsDerFree(ulong,void *)
0x1800205a7  mov     rcx, [rdi+100h]; lpMem
0x1800205ae  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x1800205b3  mov     rcx, [rdi+110h]; lpMem
0x1800205ba  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x1800205bf  mov     rcx, rdi; lpMem
0x1800205c2  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x1800205c7  lock dec cs:qword_18003AC58
0x1800205cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205d6  cmp     rcx, rbp
0x1800205d9  jz      short loc_1800205F6
0x1800205db  test    byte ptr [rcx+1Ch], 20h
0x1800205df  jz      short loc_1800205F6
0x1800205e1  mov     rcx, [rcx+10h]
0x1800205e5  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x1800205ec  mov     edx, 0Bh
0x1800205f1  call    WPP_SF_
0x1800205f6  mov     rbx, [rsp+28h+arg_0]
0x1800205fb  mov     rbp, [rsp+28h+arg_8]
0x180020600  add     rsp, 20h
0x180020604  pop     rdi
0x180020605  retn
```
