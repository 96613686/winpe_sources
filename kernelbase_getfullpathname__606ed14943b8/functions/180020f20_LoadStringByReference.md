# LoadStringByReference

- ea: `0x180020f20`
- end: `0x180021b0a`
- name: `LoadStringByReference`
- size: `3050`
- prototype: `BOOL __stdcall(DWORD Flags, PCWSTR Language, PCWSTR SourceString, PWSTR Buffer, ULONG cchBuffer, PCWSTR Directory, PULONG pcchBufferOut)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180021ee0`
- `0x18003fb50`
- `0x1800df110`

## callees

- `0x180020f20`
- `0x18004cc30`
- `0x18004ce20`
- `0x1800747f0`
- `0x180074ac8`
- `0x180083140`
- `0x1800b1050`
- `0x1800e04c0`
- `0x1800e1450`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180021180`
- `ntdll!RtlInitUnicodeString` at `0x1800211a4`
- `ntdll!RtlInitUnicodeString` at `0x180021180`
- `ntdll!RtlInitUnicodeString` at `0x1800211a4`
- `ntdll!_wcsnicmp` at `0x18002138a`
- `ntdll!_wcsnicmp` at `0x18002138a`
- `ntdll!RtlSetLastWin32Error` at `0x180021401`
- `ntdll!RtlSetLastWin32Error` at `0x180021ab6`
- `ntdll!RtlSetLastWin32Error` at `0x180021ad8`
- `ntdll!RtlSetLastWin32Error` at `0x180021401`
- `ntdll!RtlSetLastWin32Error` at `0x180021ab6`
- `ntdll!RtlSetLastWin32Error` at `0x180021ad8`
- `ntdll!RtlNtStatusToDosError` at `0x180021076`
- `ntdll!RtlNtStatusToDosError` at `0x1800213d9`
- `ntdll!RtlNtStatusToDosError` at `0x180021538`
- `ntdll!RtlNtStatusToDosError` at `0x180021599`
- `ntdll!RtlNtStatusToDosError` at `0x180021678`
- `ntdll!RtlNtStatusToDosError` at `0x180021782`
- `ntdll!RtlNtStatusToDosError` at `0x1800217b2`
- `ntdll!RtlNtStatusToDosError` at `0x1800218d8`
- `ntdll!RtlNtStatusToDosError` at `0x180021076`
- `ntdll!RtlNtStatusToDosError` at `0x1800213d9`
- `ntdll!RtlNtStatusToDosError` at `0x180021538`
- `ntdll!RtlNtStatusToDosError` at `0x180021599`
- `ntdll!RtlNtStatusToDosError` at `0x180021678`
- `ntdll!RtlNtStatusToDosError` at `0x180021782`
- `ntdll!RtlNtStatusToDosError` at `0x1800217b2`
- `ntdll!RtlNtStatusToDosError` at `0x1800218d8`
- `ntdll!RtlUnicodeStringToInteger` at `0x180021666`
- `ntdll!RtlUnicodeStringToInteger` at `0x180021666`
- `ntdll!RtlLocaleNameToLcid` at `0x18002104b`
- `ntdll!RtlLocaleNameToLcid` at `0x18002104b`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800212f0`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800212f0`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180021275`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180021275`
- `ntdll!RtlLoadString` at `0x1800218c0`
- `ntdll!RtlLoadString` at `0x1800218c0`
- `ntdll!RtlAppendUnicodeToString` at `0x180021258`
- `ntdll!RtlAppendUnicodeToString` at `0x180021770`
- `ntdll!RtlAppendUnicodeToString` at `0x1800217a0`
- `ntdll!RtlAppendUnicodeToString` at `0x180021258`
- `ntdll!RtlAppendUnicodeToString` at `0x180021770`
- `ntdll!RtlAppendUnicodeToString` at `0x1800217a0`
- `ntdll!RtlCopyUnicodeString` at `0x180021240`
- `ntdll!RtlCopyUnicodeString` at `0x180021755`
- `ntdll!RtlCopyUnicodeString` at `0x180021240`
- `ntdll!RtlCopyUnicodeString` at `0x180021755`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1800214e3`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180021587`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1800214e3`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180021587`
- `ntdll!RtlInitUnicodeStringEx` at `0x180021644`
- `ntdll!RtlInitUnicodeStringEx` at `0x180021644`
- `ntdll!NtClose` at `0x180021a8c`
- `ntdll!NtClose` at `0x180021a8c`
- `ntdll!RtlFreeHeap` at `0x1800212b1`
- `ntdll!RtlFreeHeap` at `0x1800219d6`
- `ntdll!RtlFreeHeap` at `0x180021a13`
- `ntdll!RtlFreeHeap` at `0x180021a41`
- `ntdll!RtlFreeHeap` at `0x180021a76`
- `ntdll!RtlFreeHeap` at `0x1800212b1`
- `ntdll!RtlFreeHeap` at `0x1800219d6`
- `ntdll!RtlFreeHeap` at `0x180021a13`
- `ntdll!RtlFreeHeap` at `0x180021a41`
- `ntdll!RtlFreeHeap` at `0x180021a76`
- `ntdll!RtlAllocateHeap` at `0x180021208`
- `ntdll!RtlAllocateHeap` at `0x18002151f`
- `ntdll!RtlAllocateHeap` at `0x18002170f`
- `ntdll!RtlAllocateHeap` at `0x18002197c`
- `ntdll!RtlAllocateHeap` at `0x180021208`
- `ntdll!RtlAllocateHeap` at `0x18002151f`
- `ntdll!RtlAllocateHeap` at `0x18002170f`
- `ntdll!RtlAllocateHeap` at `0x18002197c`

## string_xrefs

- `0x18002143c`: `Software\Classes\Local Settings\ImmutableMuiCache`
- `0x180021435`: `Software\Classes\Local Settings\MuiCache`

## pseudocode

```c
BOOL __stdcall LoadStringByReference(
        DWORD Flags,
        PCWSTR Language,
        PCWSTR SourceString,
        PWSTR Buffer,
        ULONG cchBuffer,
        PCWSTR Directory,
        PULONG pcchBufferOut)
{
  WCHAR *v10; // r13
  BOOL v11; // edi
  ULONG LastErrorValue; // ebx
  ULONG v13; // ecx
  __int64 v14; // rdx
  unsigned __int16 v15; // r8
  WCHAR v16; // r9
  int v17; // ecx
  WCHAR *v18; // rsi
  PCWSTR v19; // rax
  USHORT v20; // si
  int v21; // ebx
  int i; // edx
  int v23; // ecx
  const wchar_t *v24; // rcx
  int v25; // eax
  NTSTATUS v26; // ecx
  void *v27; // r12
  ULONG v28; // eax
  WCHAR *Heap; // rax
  int appended; // eax
  PWSTR v31; // r14
  int v32; // ebx
  PWSTR v33; // r15
  __int64 v34; // rdx
  int v35; // ecx
  const WCHAR *v36; // rdx
  int inited; // eax
  __int64 v38; // rax
  USHORT v39; // r14
  WCHAR *v40; // rax
  ULONG v41; // r12d
  void *v42; // r15
  HMODULE Library; // r14
  NTSTATUS v44; // eax
  __int64 v45; // r13
  unsigned int v46; // r14d
  int v47; // eax
  _WORD *v48; // rax
  _WORD *v49; // r15
  __int64 v51; // [rsp+40h] [rbp-348h] BYREF
  PCWSTR v52; // [rsp+48h] [rbp-340h]
  unsigned __int16 v53[2]; // [rsp+50h] [rbp-338h] BYREF
  ULONG Length; // [rsp+54h] [rbp-334h] BYREF
  DWORD v55; // [rsp+58h] [rbp-330h]
  unsigned int v56; // [rsp+5Ch] [rbp-32Ch] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-328h] BYREF
  unsigned int v58; // [rsp+68h] [rbp-320h] BYREF
  int v59; // [rsp+6Ch] [rbp-31Ch] BYREF
  ULONG Value; // [rsp+70h] [rbp-318h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+78h] [rbp-310h] BYREF
  PCWSTR SourceStringa; // [rsp+88h] [rbp-300h]
  void *v63; // [rsp+90h] [rbp-2F8h]
  HMODULE hLibModule; // [rsp+98h] [rbp-2F0h]
  struct _UNICODE_STRING v65; // [rsp+A0h] [rbp-2E8h] BYREF
  struct _UNICODE_STRING v66; // [rsp+B0h] [rbp-2D8h] BYREF
  int v67; // [rsp+C0h] [rbp-2C8h]
  int v68; // [rsp+C4h] [rbp-2C4h] BYREF
  void *Src; // [rsp+C8h] [rbp-2C0h] BYREF
  PCWSTR v70; // [rsp+D0h] [rbp-2B8h]
  PULONG v71; // [rsp+D8h] [rbp-2B0h]
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-2A8h] BYREF
  UNICODE_STRING v73; // [rsp+F0h] [rbp-298h] BYREF
  UNICODE_STRING String; // [rsp+100h] [rbp-288h] BYREF
  _BYTE v75[32]; // [rsp+110h] [rbp-278h] BYREF
  __int16 v76[264]; // [rsp+130h] [rbp-258h] BYREF

  v63 = Buffer;
  v70 = SourceString;
  LODWORD(v10) = Flags;
  v55 = Flags;
  hLibModule = (HMODULE)Language;
  v52 = SourceString;
  *(_QWORD *)&Destination.Length = Buffer;
  SourceStringa = Directory;
  v71 = pcchBufferOut;
  v11 = 0;
  Length = 0;
  Value = 0;
  LODWORD(v51) = 0;
  DestinationString = 0;
  v66 = 0;
  v73 = 0;
  v65 = 0;
  v53[0] = 0;
  Src = 0;
  v56 = 0;
  Handle = 0;
  v58 = 0;
  v59 = 260;
  v68 = 0;
  if ( !SourceString || !Buffer && (!pcchBufferOut || cchBuffer) || (Flags & 3) == 3 || (Flags & 0xFFFFFFE0) != 0 )
  {
    v13 = 87;
    goto LABEL_148;
  }
  LastErrorValue = 0;
  if ( Language )
  {
    if ( (int)RtlLocaleNameToLcid(Language, &v56, 3) >= 0 )
    {
      v56 = (unsigned __int16)v56;
    }
    else
    {
      LastErrorValue = 87;
      v67 = 87;
    }
  }
  if ( LastErrorValue )
  {
    v13 = LastErrorValue;
LABEL_148:
    RtlSetLastWin32Error(v13);
    return 0;
  }
  if ( *SourceString != 64 )
    goto LABEL_146;
  LODWORD(v14) = 0;
  v15 = 1;
  v16 = SourceString[1];
  if ( v16 )
  {
    do
    {
      v17 = v15;
      if ( SourceString[v15] != 44 )
        v17 = v14;
      LODWORD(v14) = v17;
      ++v15;
    }
    while ( SourceString[v15] );
  }
  if ( (_DWORD)v14 )
  {
    if ( SourceString[(unsigned int)v14] != 44
      || SourceString[(unsigned int)(v14 - 1)] == 34 && v16 != 34
      || ((unsigned __int8)v10 & 2) == 0 && (v14 = (unsigned int)(v14 + 1), SourceString[v14] != 45)
      || (unsigned __int16)(SourceString[(unsigned int)(v14 + 1)] - 48) > 9u )
    {
LABEL_146:
      v13 = 13;
      goto LABEL_148;
    }
  }
  v18 = 0;
  v52 = 0;
  hLibModule = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v19 = SourceStringa;
  if ( SourceStringa )
  {
    RtlInitUnicodeString(&v73, SourceStringa);
    v19 = SourceStringa;
  }
  if ( ((unsigned __int8)v10 & 8) != 0 || Language )
    goto LABEL_69;
  if ( v19 )
  {
    Destination = 0;
    v20 = v73.Length + DestinationString.Length + 4;
    Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v20);
    if ( Destination.Buffer )
    {
      Destination.Length = 0;
      Destination.MaximumLength = v20;
      RtlCopyUnicodeString(&Destination, &v73);
      if ( RtlAppendUnicodeToString(&Destination, L",") < 0
        || RtlAppendUnicodeStringToString(&Destination, &DestinationString) < 0 )
      {
        if ( Destination.Buffer )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
        v18 = 0;
      }
      else
      {
        v18 = Destination.Buffer;
      }
    }
    else
    {
      v18 = 0;
    }
  }
  else
  {
    v18 = (WCHAR *)SourceString;
  }
  if ( !v18 )
    goto LABEL_129;
  v76[0] = 0;
  if ( (int)RtlGetThreadPreferredUILanguages(48, &v68, v76, &v59) < 0
    || NtCurrentTeb()->MergedPrefLanguages == (PVOID)-44LL )
  {
    goto LABEL_129;
  }
  if ( ((unsigned __int8)v10 & 0x10) == 0 )
  {
    v21 = 0;
    for ( i = 1; v18[i]; ++i )
    {
      v23 = i;
      if ( v18[i] != 44 )
        v23 = v21;
      v21 = v23;
    }
    if ( v18[v21] )
    {
      while ( 1 )
      {
        v24 = &v18[v21];
        if ( *v24 == 35 && !_wcsnicmp(v24, L"#IMMUTABLE", 0xAu) )
          break;
        if ( !v18[++v21] )
          goto LABEL_53;
      }
      LODWORD(v10) = (unsigned int)v10 | 0x10;
      v55 = (unsigned int)v10;
    }
  }
LABEL_53:
  if ( ((unsigned __int8)v10 & 0x10) != 0 )
  {
    v25 = RtlStringCchPrintfW(v75, 11, L"Strings");
  }
  else
  {
    v28 = LoadGlobalCacheGeneration(&v58);
    LastErrorValue = v28;
    if ( v28 )
    {
      RtlSetLastWin32Error(v28);
      v27 = 0;
      goto LABEL_130;
    }
    v25 = RtlStringCchPrintfW(v75, 11, L"%x", v58);
  }
  if ( v25 >= 0 )
  {
    if ( !(unsigned int)OpenMuiStringCache(&Handle)
      && ((unsigned __int8)v10 & 4) == 0
      && !(unsigned int)GetMUIStringFromCache(Handle, v18, cchBuffer, (__int64)&v51) )
    {
      if ( Buffer && (unsigned int)v51 > cchBuffer )
      {
        LastErrorValue = 122;
        v27 = 0;
      }
      else
      {
        LastErrorValue = 0;
        v27 = 0;
      }
      goto LABEL_130;
    }
LABEL_69:
    v26 = RtlExpandEnvironmentStrings_U(0, &DestinationString, &v66, &Length);
    if ( (int)(v26 + 0x80000000) >= 0 && v26 != -1073741789 )
      goto LABEL_57;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
    v27 = Heap;
    if ( !Heap )
    {
LABEL_72:
      LastErrorValue = RtlNtStatusToDosError(-1073741801);
      goto LABEL_130;
    }
    v66.Buffer = Heap;
    v66.Length = 0;
    v66.MaximumLength = Length;
    v27 = 0;
    v52 = 0;
    appended = RtlExpandEnvironmentStrings_U(0, &DestinationString, &v66, &Length);
    if ( appended < 0 )
    {
LABEL_100:
      LastErrorValue = RtlNtStatusToDosError(appended);
      goto LABEL_130;
    }
    v31 = v66.Buffer;
    String = 0;
    if ( v66.Buffer && *v66.Buffer == 64 )
    {
      v32 = 0;
      v33 = v66.Buffer + 1;
      LODWORD(v34) = 1;
      if ( v66.Buffer[1] )
      {
        do
        {
          v35 = v34;
          if ( v66.Buffer[(unsigned int)v34] != 44 )
            v35 = v32;
          v32 = v35;
          v34 = (unsigned int)(v34 + 1);
        }
        while ( v66.Buffer[v34] );
      }
      if ( v32 )
      {
        if ( ((unsigned __int8)v10 & 2) != 0 )
        {
          v10 = &v66.Buffer[v32];
          v36 = v10 + 1;
LABEL_86:
          inited = RtlInitUnicodeStringEx(&String, v36);
          if ( inited >= 0 && (inited = RtlUnicodeStringToInteger(&String, 0xAu, &Value), inited >= 0) )
          {
            if ( *v33 == 34 && (v38 = (unsigned int)(v32 - 1), v31[v38] == 34) )
            {
              v31[v38] = 0;
              v33 = v31 + 2;
              LOWORD(v27) = v32 - 2;
              LastErrorValue = 0;
              LOBYTE(v10) = v55;
            }
            else
            {
              LOWORD(v27) = v32;
              *v10 = 0;
              LastErrorValue = 0;
              LOBYTE(v10) = v55;
            }
          }
          else
          {
            LastErrorValue = RtlNtStatusToDosError(inited);
            LOBYTE(v10) = v55;
          }
LABEL_95:
          if ( LastErrorValue )
            goto LABEL_58;
          if ( SourceStringa )
          {
            v39 = v73.Length + 2 * ((_WORD)v27 + 1);
            v40 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v39);
            v27 = v40;
            v52 = v40;
            if ( !v40 )
              goto LABEL_72;
            v65.Buffer = v40;
            v65.Length = 0;
            v65.MaximumLength = v39;
            RtlCopyUnicodeString(&v65, &v73);
            appended = RtlAppendUnicodeToString(&v65, L"\\");
            if ( appended < 0 )
              goto LABEL_100;
            appended = RtlAppendUnicodeToString(&v65, v33);
            if ( appended < 0 )
              goto LABEL_100;
          }
          else
          {
            v65.Buffer = v33;
            v27 = 0;
          }
          if ( ((unsigned __int8)v10 & 4) != 0 )
          {
            if ( GetFileAttributesW(v65.Buffer) == -1 )
            {
              LastErrorValue = 2;
              goto LABEL_130;
            }
            v41 = cchBuffer;
            v42 = v63;
            if ( Handle && !(unsigned int)GetMUIStringFromCache(Handle, v18, cchBuffer, (__int64)&v51) )
            {
              if ( v42 && (unsigned int)v51 > cchBuffer )
                LastErrorValue = 122;
              else
                LastErrorValue = 0;
LABEL_129:
              v27 = (void *)v52;
              goto LABEL_130;
            }
          }
          else
          {
            v42 = v63;
            v41 = cchBuffer;
          }
          Library = LoadLibraryExW(v65.Buffer, 0, 0x22u);
          hLibModule = Library;
          if ( Library )
          {
            v44 = RtlLoadString(Library, (unsigned __int16)Value, v56, 1, &Src, v53, 0, 0);
            if ( v53[0] )
            {
              v45 = v53[0];
              v46 = v53[0] + 1;
              LODWORD(v51) = v46;
              if ( v42 && v41 >= v46 )
              {
                memcpy_0(v42, Src, 2LL * v53[0]);
                *((_WORD *)v42 + v46 - 1) = 0;
              }
              else
              {
                v47 = 0;
                if ( v42 )
                  v47 = 122;
                LastErrorValue = v47;
              }
              if ( Handle )
              {
                if ( LastErrorValue || !v42 )
                {
                  v48 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * v46);
                  v49 = v48;
                  if ( v48 )
                  {
                    memcpy_0(v48, Src, 2 * v45);
                    v49[v46 - 1] = 0;
                    AddMUIStringToCache(Handle, v18, v49, (unsigned int)v51);
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v49);
                  }
                }
                else
                {
                  AddMUIStringToCache(Handle, v18, v42, (unsigned int)v51);
                }
              }
            }
            else
            {
              LastErrorValue = RtlNtStatusToDosError(v44);
              if ( !LastErrorValue )
                LastErrorValue = 1168;
            }
          }
          else
          {
            LastErrorValue = NtCurrentTeb()->LastErrorValue;
          }
          goto LABEL_129;
        }
        if ( v66.Buffer[v32 + 1] == 45 )
        {
          v10 = &v66.Buffer[v32];
          v36 = v10 + 2;
          goto LABEL_86;
        }
      }
    }
    else
    {
      v33 = 0;
    }
    LastErrorValue = 13;
    goto LABEL_95;
  }
  v26 = v25;
LABEL_57:
  LastErrorValue = RtlNtStatusToDosError(v26);
LABEL_58:
  v27 = 0;
LABEL_130:
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( v27 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27);
  if ( v66.Buffer )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v66.Buffer);
    v66.Buffer = 0;
  }
  if ( v18 && v18 != v70 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
  if ( Handle )
    NtClose(Handle);
  if ( !LastErrorValue || LastErrorValue == 122 )
  {
    if ( v71 )
      *v71 = v51;
  }
  RtlSetLastWin32Error(LastErrorValue);
  LOBYTE(v11) = LastErrorValue == 0;
  return v11;
}

```

## disassembly

```asm
0x180020f20  mov     [rsp+arg_0], ecx
0x180020f24  push    rbx
0x180020f25  push    rsi
0x180020f26  push    rdi
0x180020f27  push    r12
0x180020f29  push    r13
0x180020f2b  push    r14
0x180020f2d  push    r15
0x180020f2f  sub     rsp, 350h
0x180020f36  mov     rax, cs:__security_cookie
0x180020f3d  xor     rax, rsp
0x180020f40  mov     [rsp+388h+var_48], rax
0x180020f48  mov     r12, r9
0x180020f4b  mov     [rsp+388h+var_2F8], r9
0x180020f53  mov     r15, r8
0x180020f56  mov     [rsp+388h+var_2B8], r8
0x180020f5e  mov     r14, rdx
0x180020f61  mov     r13d, ecx
0x180020f64  mov     [rsp+388h+var_330], ecx
0x180020f68  mov     [rsp+388h+hLibModule], rdx
0x180020f70  mov     [rsp+388h+var_340], r8
0x180020f75  mov     qword ptr [rsp+388h+Destination.Length], r9
0x180020f7a  mov     rcx, [rsp+388h+Directory]
0x180020f82  mov     [rsp+388h+SourceString], rcx
0x180020f8a  mov     rcx, [rsp+388h+pcchBufferOut]
0x180020f92  mov     [rsp+388h+var_2B0], rcx
0x180020f9a  xor     edi, edi
0x180020f9c  mov     [rsp+388h+Length], edi
0x180020fa0  mov     [rsp+388h+Value], edi
0x180020fa4  mov     dword ptr [rsp+388h+var_348], edi
0x180020fa8  xorps   xmm0, xmm0
0x180020fab  movups  xmmword ptr [rsp+388h+DestinationString.Length], xmm0
0x180020fb3  xorps   xmm1, xmm1
0x180020fb6  movups  xmmword ptr [rsp+388h+var_2D8.Length], xmm1
0x180020fbe  movups  xmmword ptr [rsp+388h+var_298.Length], xmm0
0x180020fc6  movups  xmmword ptr [rsp+388h+var_2E8.Length], xmm1
0x180020fce  mov     [rsp+388h+var_338], di
0x180020fd3  mov     [rsp+388h+Src], rdi
0x180020fdb  mov     [rsp+388h+var_32C], edi
0x180020fdf  mov     [rsp+388h+Handle], rdi
0x180020fe4  mov     [rsp+388h+var_320], edi
0x180020fe8  mov     [rsp+388h+var_31C], 104h
0x180020ff0  mov     [rsp+388h+var_2C4], edi
0x180020ff7  test    r8, r8
0x180020ffa  jz      loc_180021AD3
0x180021000  test    r9, r9
0x180021003  jnz     short loc_18002101B
0x180021005  test    rcx, rcx
0x180021008  jz      loc_180021AD3
0x18002100e  cmp     [rsp+388h+cchBuffer], edi
0x180021015  jnz     loc_180021AD3
0x18002101b  mov     eax, r13d
0x18002101e  and     eax, 3
0x180021021  cmp     al, 3
0x180021023  jz      loc_180021AD3
0x180021029  test    r13d, 0FFFFFFE0h
0x180021030  jnz     loc_180021AD3
0x180021036  mov     ebx, edi
0x180021038  test    r14, r14
0x18002103b  jz      short loc_1800210BC
0x18002103d  mov     r8d, 3
0x180021043  lea     rdx, [rsp+388h+var_32C]
0x180021048  mov     rcx, r14
0x18002104b  call    cs:__imp_RtlLocaleNameToLcid
0x180021052  nop     dword ptr [rax+rax+00h]
0x180021057  test    eax, eax
0x180021059  jns     short loc_180021069
0x18002105b  mov     ebx, 57h ; 'W'
0x180021060  mov     [rsp+388h+var_2C8], ebx
0x180021067  jmp     short loc_180021072
0x180021069  movzx   eax, word ptr [rsp+388h+var_32C]
0x18002106e  mov     [rsp+388h+var_32C], eax
0x180021072  jmp     short loc_1800210BC
0x180021074  mov     ecx, eax; Status
0x180021076  call    cs:__imp_RtlNtStatusToDosError
0x18002107d  nop     dword ptr [rax+rax+00h]
0x180021082  mov     ebx, eax
0x180021084  mov     [rsp+388h+var_2C8], eax
0x18002108b  xor     edi, edi
0x18002108d  mov     r13d, [rsp+388h+arg_0]
0x180021095  mov     [rsp+388h+var_330], r13d
0x18002109a  mov     r14, [rsp+388h+hLibModule]
0x1800210a2  mov     r15, [rsp+388h+var_340]
0x1800210a7  mov     [rsp+388h+var_2B8], r15
0x1800210af  mov     r12, qword ptr [rsp+388h+Destination.Length]
0x1800210b4  mov     [rsp+388h+var_2F8], r12
0x1800210bc  test    ebx, ebx
0x1800210be  jz      short loc_1800210C7
0x1800210c0  mov     ecx, ebx
0x1800210c2  jmp     loc_180021AD8
0x1800210c7  cmp     word ptr [r15], 40h ; '@'
0x1800210cc  jnz     loc_180021ACC
0x1800210d2  mov     edx, edi
0x1800210d4  mov     r8d, 1
0x1800210da  movzx   r9d, word ptr [r15+2]
0x1800210df  test    r9w, r9w
0x1800210e3  jz      short loc_180021113
0x1800210e5  nop     word ptr [rax+rax+00000000h]
0x1800210f0  movzx   eax, r8w
0x1800210f4  movzx   ecx, r8w
0x1800210f8  cmp     word ptr [r15+rax*2], 2Ch ; ','
0x1800210fe  cmovnz  ecx, edx
0x180021101  mov     edx, ecx
0x180021103  inc     r8w
0x180021107  movzx   eax, r8w
0x18002110b  cmp     word ptr [r15+rax*2], 0
0x180021111  jnz     short loc_1800210F0
0x180021113  test    edx, edx
0x180021115  jz      short loc_180021165
0x180021117  mov     eax, edx
0x180021119  cmp     word ptr [r15+rax*2], 2Ch ; ','
0x18002111f  jnz     loc_180021ACC
0x180021125  lea     eax, [rdx-1]
0x180021128  cmp     word ptr [r15+rax*2], 22h ; '"'
0x18002112e  jnz     short loc_18002113B
0x180021130  cmp     r9w, 22h ; '"'
0x180021135  jnz     loc_180021ACC
0x18002113b  test    r13b, 2
0x18002113f  jnz     short loc_18002114F
0x180021141  inc     edx
0x180021143  cmp     word ptr [r15+rdx*2], 2Dh ; '-'
0x180021149  jnz     loc_180021ACC
0x18002114f  lea     eax, [rdx+1]
0x180021152  movzx   eax, word ptr [r15+rax*2]
0x180021157  sub     ax, 30h ; '0'
0x18002115b  cmp     ax, 9
0x18002115f  ja      loc_180021ACC
0x180021165  mov     rsi, rdi
0x180021168  mov     [rsp+388h+var_340], rdi
0x18002116d  mov     [rsp+388h+hLibModule], rdi
0x180021175  mov     rdx, r15; SourceString
0x180021178  lea     rcx, [rsp+388h+DestinationString]; DestinationString
0x180021180  call    cs:__imp_RtlInitUnicodeString
0x180021187  nop     dword ptr [rax+rax+00h]
0x18002118c  mov     rax, [rsp+388h+SourceString]
0x180021194  test    rax, rax
0x180021197  jz      short loc_1800211B8
0x180021199  mov     rdx, rax; SourceString
0x18002119c  lea     rcx, [rsp+388h+var_298]; DestinationString
0x1800211a4  call    cs:__imp_RtlInitUnicodeString
0x1800211ab  nop     dword ptr [rax+rax+00h]
0x1800211b0  mov     rax, [rsp+388h+SourceString]
0x1800211b8  test    r13b, 8
0x1800211bc  jnz     loc_1800214CC
0x1800211c2  test    r14, r14
0x1800211c5  jnz     loc_1800214CC
0x1800211cb  test    rax, rax
0x1800211ce  jz      loc_1800212C2
0x1800211d4  xorps   xmm0, xmm0
0x1800211d7  movups  xmmword ptr [rsp+388h+Destination.Length], xmm0
0x1800211dc  movzx   eax, [rsp+388h+DestinationString.Length]
0x1800211e4  add     ax, 4
0x1800211e8  add     ax, [rsp+388h+var_298.Length]
0x1800211f0  movzx   esi, ax
0x1800211f3  mov     r8d, esi; Size
0x1800211f6  mov     rcx, gs:60h
0x1800211ff  mov     edx, 8; Flags
0x180021204  mov     rcx, [rcx+30h]; HeapHandle
0x180021208  call    cs:__imp_RtlAllocateHeap
0x18002120f  nop     dword ptr [rax+rax+00h]
0x180021214  mov     [rsp+388h+Destination.Buffer], rax
0x18002121c  test    rax, rax
0x18002121f  jnz     short loc_180021229
0x180021221  mov     rsi, rdi
0x180021224  jmp     loc_1800212C5
0x180021229  mov     [rsp+388h+Destination.Length], di
0x18002122e  mov     [rsp+388h+Destination.MaximumLength], si
0x180021233  lea     rdx, [rsp+388h+var_298]; SourceString
0x18002123b  lea     rcx, [rsp+388h+Destination]; DestinationString
0x180021240  call    cs:__imp_RtlCopyUnicodeString
0x180021247  nop     dword ptr [rax+rax+00h]
0x18002124c  lea     rdx, Source; ","
0x180021253  lea     rcx, [rsp+388h+Destination]; Destination
0x180021258  call    cs:__imp_RtlAppendUnicodeToString
0x18002125f  nop     dword ptr [rax+rax+00h]
0x180021264  test    eax, eax
0x180021266  js      short loc_18002128F
0x180021268  lea     rdx, [rsp+388h+DestinationString]; Source
0x180021270  lea     rcx, [rsp+388h+Destination]; Destination
0x180021275  call    cs:__imp_RtlAppendUnicodeStringToString
0x18002127c  nop     dword ptr [rax+rax+00h]
0x180021281  test    eax, eax
0x180021283  js      short loc_18002128F
0x180021285  mov     rsi, [rsp+388h+Destination.Buffer]
0x18002128d  jmp     short loc_1800212C5
0x18002128f  cmp     [rsp+388h+Destination.Buffer], 0
0x180021298  jz      short loc_1800212BD
0x18002129a  mov     rcx, gs:60h
0x1800212a3  mov     r8, [rsp+388h+Destination.Buffer]; P
0x1800212ab  xor     edx, edx; Flags
0x1800212ad  mov     rcx, [rcx+30h]; HeapHandle
0x1800212b1  call    cs:__imp_RtlFreeHeap
0x1800212b8  nop     dword ptr [rax+rax+00h]
0x1800212bd  mov     rsi, rdi
0x1800212c0  jmp     short loc_1800212C5
0x1800212c2  mov     rsi, r15
0x1800212c5  test    rsi, rsi
0x1800212c8  jz      loc_1800219E2
0x1800212ce  mov     [rsp+388h+var_258], di
0x1800212d6  lea     r9, [rsp+388h+var_31C]
0x1800212db  lea     r8, [rsp+388h+var_258]
0x1800212e3  lea     rdx, [rsp+388h+var_2C4]
0x1800212eb  mov     ecx, 30h ; '0'
0x1800212f0  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x1800212f7  nop     dword ptr [rax+rax+00h]
0x1800212fc  test    eax, eax
0x1800212fe  js      loc_1800219E2
0x180021304  mov     rax, gs:30h
0x18002130d  mov     r15, [rax+17E0h]
0x180021314  add     r15, 2Ch ; ','
0x180021318  jz      loc_1800219E2
0x18002131e  test    r13b, 10h
0x180021322  jnz     loc_1800213B1
0x180021328  mov     ebx, edi
0x18002132a  mov     edx, 1
0x18002132f  cmp     word ptr [rsi+2], 0
0x180021334  jz      short loc_18002135B
0x180021336  nop     word ptr [rax+rax+00000000h]
0x180021340  movsxd  rax, edx
0x180021343  mov     ecx, edx
0x180021345  cmp     word ptr [rsi+rax*2], 2Ch ; ','
0x18002134a  cmovnz  ecx, ebx
0x18002134d  mov     ebx, ecx
0x18002134f  inc     edx
0x180021351  movsxd  rax, edx
0x180021354  cmp     word ptr [rsi+rax*2], 0
0x180021359  jnz     short loc_180021340
0x18002135b  movsxd  rax, ebx
0x18002135e  cmp     word ptr [rsi+rax*2], 0
0x180021363  jz      short loc_1800213B1
0x180021365  nop     word ptr [rax+rax+00000000h]
0x180021370  movsxd  rax, ebx
0x180021373  lea     rcx, [rsi+rax*2]; String1
0x180021377  cmp     word ptr [rcx], 23h ; '#'
0x18002137b  jnz     short loc_18002139A
0x18002137d  mov     r8d, 0Ah; MaxCount
0x180021383  lea     rdx, aImmutable; "#IMMUTABLE"
0x18002138a  call    cs:__imp__wcsnicmp
0x180021391  nop     dword ptr [rax+rax+00h]
0x180021396  test    eax, eax
0x180021398  jz      short loc_1800213A8
0x18002139a  inc     ebx
0x18002139c  movsxd  rax, ebx
0x18002139f  cmp     word ptr [rsi+rax*2], 0
0x1800213a4  jnz     short loc_180021370
0x1800213a6  jmp     short loc_1800213B1
0x1800213a8  or      r13d, 10h
0x1800213ac  mov     [rsp+388h+var_330], r13d
0x1800213b1  mov     r14d, r13d
0x1800213b4  and     r14d, 10h
0x1800213b8  jz      short loc_1800213EF
0x1800213ba  lea     r8, aStrings; "Strings"
0x1800213c1  mov     edx, 0Bh
0x1800213c6  lea     rcx, [rsp+388h+var_278]
0x1800213ce  call    RtlStringCchPrintfW
0x1800213d3  test    eax, eax
0x1800213d5  jns     short loc_180021435
0x1800213d7  mov     ecx, eax; Status
0x1800213d9  call    cs:__imp_RtlNtStatusToDosError
0x1800213e0  nop     dword ptr [rax+rax+00h]
0x1800213e5  mov     ebx, eax
0x1800213e7  mov     r12, rdi
0x1800213ea  jmp     loc_1800219E7
0x1800213ef  lea     rcx, [rsp+388h+var_320]
0x1800213f4  call    _LoadGlobalCacheGeneration
0x1800213f9  mov     ebx, eax
0x1800213fb  test    eax, eax
0x1800213fd  jz      short loc_180021415
0x1800213ff  mov     ecx, eax; LastError
0x180021401  call    cs:__imp_RtlSetLastWin32Error
0x180021408  nop     dword ptr [rax+rax+00h]
0x18002140d  mov     r12, rdi
0x180021410  jmp     loc_1800219E7
0x180021415  mov     r9d, [rsp+388h+var_320]
0x18002141a  lea     r8, asc_1802A4E70; "%x"
0x180021421  mov     edx, 0Bh
0x180021426  lea     rcx, [rsp+388h+var_278]
0x18002142e  call    RtlStringCchPrintfW
0x180021433  jmp     short loc_1800213D3
0x180021435  lea     rax, aSoftwareClasse; "Software\\Classes\\Local Settings\\MuiC"...
0x18002143c  lea     rdx, aSoftwareClasse_5; "Software\\Classes\\Local Settings\\Immu"...
0x180021443  test    r14d, r14d
0x180021446  cmovz   rdx, rax
0x18002144a  mov     eax, [rsp+388h+var_31C]
0x18002144e  mov     dword ptr [rsp+388h+var_360], eax
0x180021452  lea     rax, [rsp+388h+var_258]
0x18002145a  mov     qword ptr [rsp+388h+var_368], rax
0x18002145f  mov     r9, r15
0x180021462  lea     r8, [rsp+388h+var_278]
0x18002146a  lea     rcx, [rsp+388h+Handle]; KeyHandle
0x18002146f  call    _OpenMuiStringCache
0x180021474  test    eax, eax
0x180021476  jnz     short loc_1800214CC
0x180021478  test    r13b, 4
0x18002147c  jnz     short loc_1800214CC
0x18002147e  lea     rax, [rsp+388h+var_348]
0x180021483  mov     [rsp+388h+var_360], rax; __int64
0x180021488  mov     ebx, [rsp+388h+cchBuffer]
0x18002148f  mov     [rsp+388h+var_368], ebx; int
0x180021493  mov     r9, r12
  ... truncated ...
```
