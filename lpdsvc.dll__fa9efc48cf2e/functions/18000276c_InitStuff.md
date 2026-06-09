# InitStuff

- ea: `0x18000276c`
- end: `0x18000296d`
- name: `InitStuff`
- size: `513`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007c10`

## callees

- `0x18000276c`
- `0x180002974`
- `0x180002b68`
- `0x180002dfc`
- `0x180002e7c`

## import_xrefs

- `KERNEL32!CreateSemaphoreA` at `0x18000290d`
- `KERNEL32!CreateSemaphoreA` at `0x18000290d`
- `KERNEL32!GetVersion` at `0x1800028d3`
- `KERNEL32!GetVersion` at `0x1800028d3`
- `KERNEL32!InitializeCriticalSection` at `0x1800028c8`
- `KERNEL32!InitializeCriticalSection` at `0x1800028c8`
- `KERNEL32!CreateEventA` at `0x180002868`
- `KERNEL32!CreateEventA` at `0x18000287f`
- `KERNEL32!CreateEventA` at `0x180002868`
- `KERNEL32!CreateEventA` at `0x18000287f`
- `ADVAPI32!RegisterEventSourceA` at `0x180002802`
- `ADVAPI32!RegisterEventSourceA` at `0x180002802`

## pseudocode

```c
__int64 InitStuff()
{
  _QWORD *v0; // rcx
  __int64 v1; // rdx
  _QWORD *v2; // rcx
  HANDLE EventA; // rax
  unsigned __int16 Version; // ax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_e2a11bdbf6a53dd330d768a48b9244ec_Traceguids);
  if ( !(unsigned int)LoadStrings() )
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return 0;
    v1 = 18;
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_90a417783231378e8d16226d33123045_Traceguids);
  hLogHandleGLB = RegisterEventSourceA(0, "LPDSVC");
  if ( !hLogHandleGLB )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_90a417783231378e8d16226d33123045_Traceguids);
        v2 = WPP_GLOBAL_Control;
      }
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 )
        WPP_SF_(v2[2], 19, &WPP_e2a11bdbf6a53dd330d768a48b9244ec_Traceguids);
    }
  }
  hEventShutdownGLB = CreateEventA(0, 1, 0, 0);
  EventA = CreateEventA(0, 0, 0, 0);
  hEventLastThreadGLB = EventA;
  if ( !hEventShutdownGLB || !EventA )
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return 0;
    v1 = 20;
    goto LABEL_28;
  }
  scConnHeadGLB = 0;
  Common = 0;
  qword_180013710 = 0;
  InitializeCriticalSection(&csConnSemGLB);
  ReadRegistryValues();
  Version = GetVersion();
  StringCchPrintfA(szNTVersion, 8u, "%d.%d", (unsigned __int8)Version, HIBYTE(Version));
  hWorkThreadSemaphore = CreateSemaphoreA(0, 0, MaxQueueLength, 0);
  if ( hWorkThreadSemaphore )
    return 1;
  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v1 = 21;
LABEL_28:
    WPP_SF_(v0[2], v1, &WPP_e2a11bdbf6a53dd330d768a48b9244ec_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18000276c  mov     [rsp+arg_0], rbx
0x180002771  push    rdi
0x180002772  sub     rsp, 30h
0x180002776  mov     rcx, cs:WPP_GLOBAL_Control
0x18000277d  lea     rbx, WPP_GLOBAL_Control
0x180002784  lea     rdi, WPP_e2a11bdbf6a53dd330d768a48b9244ec_Traceguids
0x18000278b  cmp     rcx, rbx
0x18000278e  jz      short loc_1800027A7
0x180002790  test    byte ptr [rcx+1Ch], 1
0x180002794  jz      short loc_1800027A7
0x180002796  mov     rcx, [rcx+10h]
0x18000279a  mov     edx, 11h
0x18000279f  mov     r8, rdi
0x1800027a2  call    WPP_SF_
0x1800027a7  call    LoadStrings
0x1800027ac  test    eax, eax
0x1800027ae  jnz     short loc_1800027D2
0x1800027b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027b7  cmp     rcx, rbx
0x1800027ba  jz      loc_180002960
0x1800027c0  test    byte ptr [rcx+1Ch], 8
0x1800027c4  jz      loc_180002960
0x1800027ca  lea     edx, [rax+12h]
0x1800027cd  jmp     loc_180002954
0x1800027d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027d9  cmp     rcx, rbx
0x1800027dc  jz      short loc_1800027F9
0x1800027de  test    byte ptr [rcx+1Ch], 1
0x1800027e2  jz      short loc_1800027F9
0x1800027e4  mov     rcx, [rcx+10h]
0x1800027e8  lea     r8, WPP_90a417783231378e8d16226d33123045_Traceguids
0x1800027ef  mov     edx, 0Ah
0x1800027f4  call    WPP_SF_
0x1800027f9  lea     rdx, ServiceName; "LPDSVC"
0x180002800  xor     ecx, ecx; lpUNCServerName
0x180002802  call    cs:__imp_RegisterEventSourceA
0x180002808  mov     cs:hLogHandleGLB, rax
0x18000280f  test    rax, rax
0x180002812  jnz     short loc_18000285C
0x180002814  mov     rcx, cs:WPP_GLOBAL_Control
0x18000281b  cmp     rcx, rbx
0x18000281e  jz      short loc_18000285C
0x180002820  test    byte ptr [rcx+1Ch], 8
0x180002824  jz      short loc_180002840
0x180002826  mov     rcx, [rcx+10h]
0x18000282a  lea     edx, [rax+0Bh]
0x18000282d  lea     r8, WPP_90a417783231378e8d16226d33123045_Traceguids
0x180002834  call    WPP_SF_
0x180002839  mov     rcx, cs:WPP_GLOBAL_Control
0x180002840  cmp     rcx, rbx
0x180002843  jz      short loc_18000285C
0x180002845  test    byte ptr [rcx+1Ch], 4
0x180002849  jz      short loc_18000285C
0x18000284b  mov     rcx, [rcx+10h]
0x18000284f  mov     edx, 13h
0x180002854  mov     r8, rdi
0x180002857  call    WPP_SF_
0x18000285c  xor     r9d, r9d; lpName
0x18000285f  xor     r8d, r8d; bInitialState
0x180002862  xor     ecx, ecx; lpEventAttributes
0x180002864  lea     edx, [r9+1]; bManualReset
0x180002868  call    cs:__imp_CreateEventA
0x18000286e  xor     r9d, r9d; lpName
0x180002871  xor     r8d, r8d; bInitialState
0x180002874  xor     edx, edx; bManualReset
0x180002876  mov     cs:hEventShutdownGLB, rax
0x18000287d  xor     ecx, ecx; lpEventAttributes
0x18000287f  call    cs:__imp_CreateEventA
0x180002885  cmp     cs:hEventShutdownGLB, 0
0x18000288d  mov     cs:hEventLastThreadGLB, rax
0x180002894  jz      loc_18000293D
0x18000289a  test    rax, rax
0x18000289d  jz      loc_18000293D
0x1800028a3  xorps   xmm0, xmm0
0x1800028a6  mov     cs:scConnHeadGLB, 0
0x1800028b1  xor     eax, eax
0x1800028b3  lea     rcx, csConnSemGLB; lpCriticalSection
0x1800028ba  movups  cs:Common, xmm0
0x1800028c1  mov     cs:qword_180013710, rax
0x1800028c8  call    cs:__imp_InitializeCriticalSection
0x1800028ce  call    ReadRegistryValues
0x1800028d3  call    cs:__imp_GetVersion
0x1800028d9  movzx   ecx, ax
0x1800028dc  lea     r8, pszFormat; "%d.%d"
0x1800028e3  shr     ecx, 8
0x1800028e6  mov     edx, 8; cchDest
0x1800028eb  mov     [rsp+38h+var_18], ecx
0x1800028ef  lea     rcx, szNTVersion; pszDest
0x1800028f6  movzx   r9d, al
0x1800028fa  call    StringCchPrintfA
0x1800028ff  mov     r8d, cs:MaxQueueLength; lMaximumCount
0x180002906  xor     r9d, r9d; lpName
0x180002909  xor     edx, edx; lInitialCount
0x18000290b  xor     ecx, ecx; lpSemaphoreAttributes
0x18000290d  call    cs:__imp_CreateSemaphoreA
0x180002913  mov     cs:hWorkThreadSemaphore, rax
0x18000291a  test    rax, rax
0x18000291d  jnz     short loc_180002936
0x18000291f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002926  cmp     rcx, rbx
0x180002929  jz      short loc_180002960
0x18000292b  test    byte ptr [rcx+1Ch], 8
0x18000292f  jz      short loc_180002960
0x180002931  lea     edx, [rax+15h]
0x180002934  jmp     short loc_180002954
0x180002936  mov     eax, 1
0x18000293b  jmp     short loc_180002962
0x18000293d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002944  cmp     rcx, rbx
0x180002947  jz      short loc_180002960
0x180002949  test    byte ptr [rcx+1Ch], 8
0x18000294d  jz      short loc_180002960
0x18000294f  mov     edx, 14h
0x180002954  mov     rcx, [rcx+10h]
0x180002958  mov     r8, rdi
0x18000295b  call    WPP_SF_
0x180002960  xor     eax, eax
0x180002962  mov     rbx, [rsp+38h+arg_0]
0x180002967  add     rsp, 30h
0x18000296b  pop     rdi
0x18000296c  retn
```
