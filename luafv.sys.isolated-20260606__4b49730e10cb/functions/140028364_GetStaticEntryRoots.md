# GetStaticEntryRoots

- ea: `0x140028364`
- end: `0x14002870c`
- name: `GetStaticEntryRoots`
- size: `936`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140029784`

## callees

- `0x140014b1c`
- `0x14001b6a0`
- `0x14001dd90`
- `0x140028008`
- `0x14002814c`
- `0x140028364`
- `0x140028f24`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140028570`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140028644`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140028570`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140028644`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400284c9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400284c9`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x1400283cd`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x1400283cd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400284b2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140028559`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140028630`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400284b2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140028559`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140028630`
- `ntoskrnl!ZwClose` at `0x140028407`
- `ntoskrnl!ZwClose` at `0x140028696`
- `ntoskrnl!ZwClose` at `0x1400286c3`
- `ntoskrnl!ZwClose` at `0x1400286d8`
- `ntoskrnl!ZwClose` at `0x140028407`
- `ntoskrnl!ZwClose` at `0x140028696`
- `ntoskrnl!ZwClose` at `0x1400286c3`
- `ntoskrnl!ZwClose` at `0x1400286d8`

## pseudocode

```c
__int64 GetStaticEntryRoots()
{
  int appended; // ebx
  __int64 v1; // r8
  USHORT v2; // bx
  __int64 v3; // r8
  unsigned int i; // edi
  __int64 v5; // rsi
  unsigned int v6; // r15d
  __int64 *v7; // r14
  __int64 v8; // r8
  __int64 v9; // rax
  UNICODE_STRING Source; // [rsp+20h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-19h] BYREF
  UNICODE_STRING LinkTarget; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  void *LinkHandle; // [rsp+C0h] [rbp+67h] BYREF
  HANDLE Handle; // [rsp+C8h] [rbp+6Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  LinkHandle = 0;
  Handle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&SystemRootLinkName;
  LinkTarget = 0;
  SourceString = 0;
  Source = 0;
  DestinationString = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  appended = ZwOpenSymbolicLinkObject(&LinkHandle, 1u, &ObjectAttributes);
  if ( appended >= 0 )
  {
    appended = QuerySymbolicLink(LinkHandle, &LinkTarget);
    if ( appended >= 0 )
    {
      ZwClose(LinkHandle);
      LinkHandle = 0;
      appended = TranslatePath(&LinkTarget.Length, &SourceString, &Source);
      if ( appended >= 0 )
      {
        StaticEntryRoots[0] = (__int128)SourceString;
        v2 = SourceString.Length + 4;
        stru_14000F128 = SourceString;
        if ( (unsigned __int16)(SourceString.Length + 4) < SourceString.Length )
        {
          appended = -1073741675;
        }
        else
        {
          LOBYTE(v1) = 2;
          DestinationString.Buffer = (PWSTR)LuafvAllocatePool(1, (unsigned __int16)(SourceString.Length + 4), v1);
          if ( DestinationString.Buffer )
          {
            DestinationString.MaximumLength = v2;
            DestinationString.Length = 0;
            RtlCopyUnicodeString(&DestinationString, &stru_14000F128);
            appended = RtlAppendUnicodeToString(&DestinationString, L"\\");
            if ( appended >= 0 )
            {
              String1 = DestinationString;
              LOBYTE(v3) = 1;
              Destination.MaximumLength = SourceString.Length + Source.Length;
              DestinationString = 0;
              Destination.Buffer = (PWSTR)LuafvAllocatePool(
                                            1,
                                            (unsigned __int16)(SourceString.Length + Source.Length),
                                            v3);
              if ( Destination.Buffer )
              {
                RtlCopyUnicodeString(&Destination, &SourceString);
                RtlAppendUnicodeStringToString(&Destination, &Source);
                LuafvFreePool(Source.Buffer);
                for ( i = 0; i < 2; ++i )
                {
                  v5 = 2LL * i;
                  appended = LuafvOpenKey(0, (struct _UNICODE_STRING *)(0x140000000LL + v5 * 8 + 176496), &Handle);
                  if ( appended < 0 )
                    goto LABEL_23;
                  v6 = 0;
                  v7 = (&RegistryStaticRoots)[v5];
                  while ( v6 < LODWORD(qword_14002B140[v5]) )
                  {
                    appended = QueryStringValue(Handle, (PUNICODE_STRING)v7);
                    if ( appended < 0 )
                      goto LABEL_23;
                    LOBYTE(v8) = 1;
                    Source.MaximumLength = GlobalRoot.Length + LinkTarget.Length;
                    Source.Buffer = (PWSTR)LuafvAllocatePool(
                                             1,
                                             (unsigned __int16)(GlobalRoot.Length + LinkTarget.Length),
                                             v8);
                    if ( !Source.Buffer )
                      goto LABEL_7;
                    RtlCopyUnicodeString(&Source, &GlobalRoot);
                    RtlAppendUnicodeStringToString(&Source, &LinkTarget);
                    appended = TranslatePath(&Source.Length, &SourceString, 0);
                    LuafvFreePool(Source.Buffer);
                    if ( appended < 0 )
                      goto LABEL_23;
                    v9 = *((int *)v7 + 4);
                    ++v6;
                    v7 += 3;
                    StaticEntryRoots[v9] = (__int128)SourceString;
                  }
                  ZwClose(Handle);
                  Handle = 0;
                }
                appended = 0;
              }
              else
              {
                appended = -1073741670;
                LuafvFreePool(Source.Buffer);
              }
            }
          }
          else
          {
LABEL_7:
            appended = -1073741670;
          }
        }
      }
    }
LABEL_23:
    if ( LinkHandle )
      ZwClose(LinkHandle);
  }
  else
  {
    LinkHandle = 0;
  }
  if ( Handle )
    ZwClose(Handle);
  if ( DestinationString.Buffer )
    LuafvFreePool(DestinationString.Buffer);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140028364  mov     [rsp-8+arg_10], rbx
0x140028369  push    rbp
0x14002836a  push    rsi
0x14002836b  push    rdi
0x14002836c  push    r14
0x14002836e  push    r15
0x140028370  lea     rbp, [rsp-37h]
0x140028375  sub     rsp, 90h
0x14002837c  xor     eax, eax
0x14002837e  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140028386  xorps   xmm0, xmm0
0x140028389  mov     [rbp+57h+LinkHandle], rax
0x14002838d  mov     [rbp+57h+Handle], rax
0x140028391  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140028395  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140028399  lea     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x14002839d  lea     rax, SystemRootLinkName
0x1400283a4  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400283ac  xorps   xmm1, xmm1
0x1400283af  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400283b3  mov     edx, 1; DesiredAccess
0x1400283b8  movups  xmmword ptr [rbp+57h+LinkTarget.Length], xmm0
0x1400283bc  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm1
0x1400283c0  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x1400283c4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400283c8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400283cd  call    cs:__imp_ZwOpenSymbolicLinkObject
0x1400283d4  nop     dword ptr [rax+rax+00h]
0x1400283d9  mov     ebx, eax
0x1400283db  test    eax, eax
0x1400283dd  jns     short loc_1400283EC
0x1400283df  mov     [rbp+57h+LinkHandle], 0
0x1400283e7  jmp     loc_1400286CF
0x1400283ec  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x1400283f0  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x1400283f4  call    QuerySymbolicLink
0x1400283f9  mov     ebx, eax
0x1400283fb  test    eax, eax
0x1400283fd  js      loc_1400286BA
0x140028403  mov     rcx, [rbp+57h+LinkHandle]; Handle
0x140028407  call    cs:__imp_ZwClose
0x14002840e  nop     dword ptr [rax+rax+00h]
0x140028413  lea     r8, [rbp+57h+Source]
0x140028417  mov     [rbp+57h+LinkHandle], 0
0x14002841f  lea     rdx, [rbp+57h+SourceString]
0x140028423  lea     rcx, [rbp+57h+LinkTarget]
0x140028427  call    TranslatePath
0x14002842c  mov     ebx, eax
0x14002842e  test    eax, eax
0x140028430  js      loc_1400286BA
0x140028436  movzx   ecx, [rbp+57h+SourceString.Length]
0x14002843a  movsd   xmm0, qword ptr [rbp+57h+SourceString.MaximumLength]
0x14002843f  mov     eax, dword ptr [rbp+57h+SourceString.Buffer+2]
0x140028442  movsd   qword ptr cs:StaticEntryRoots+2, xmm0
0x14002844a  movups  xmm0, xmmword ptr [rbp+57h+SourceString.Length]
0x14002844e  lea     ebx, [rcx+4]
0x140028451  mov     dword ptr cs:StaticEntryRoots+0Ah, eax
0x140028457  movzx   eax, word ptr [rbp+57h+SourceString.Buffer+6]
0x14002845b  mov     word ptr cs:StaticEntryRoots, cx
0x140028462  mov     word ptr cs:StaticEntryRoots+0Eh, ax
0x140028469  movdqu  xmmword ptr cs:stru_14000F128.Length, xmm0
0x140028471  cmp     bx, cx
0x140028474  jb      loc_1400286B5
0x14002847a  movzx   edx, bx
0x14002847d  mov     r8b, 2
0x140028480  mov     ecx, 1
0x140028485  call    LuafvAllocatePool
0x14002848a  mov     [rbp+57h+DestinationString.Buffer], rax
0x14002848e  test    rax, rax
0x140028491  jnz     short loc_14002849D
0x140028493  mov     ebx, 0C000009Ah
0x140028498  jmp     loc_1400286BA
0x14002849d  xor     eax, eax
0x14002849f  mov     [rbp+57h+DestinationString.MaximumLength], bx
0x1400284a3  lea     rdx, stru_14000F128; SourceString
0x1400284aa  mov     [rbp+57h+DestinationString.Length], ax
0x1400284ae  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400284b2  call    cs:__imp_RtlCopyUnicodeString
0x1400284b9  nop     dword ptr [rax+rax+00h]
0x1400284be  lea     rdx, Source; "\\"
0x1400284c5  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1400284c9  call    cs:__imp_RtlAppendUnicodeToString
0x1400284d0  nop     dword ptr [rax+rax+00h]
0x1400284d5  mov     ebx, eax
0x1400284d7  test    eax, eax
0x1400284d9  js      loc_1400286BA
0x1400284df  movzx   eax, [rbp+57h+DestinationString.Length]
0x1400284e3  xorps   xmm0, xmm0
0x1400284e6  mov     cs:String1.Length, ax
0x1400284ed  mov     r8b, 1
0x1400284f0  movzx   eax, [rbp+57h+DestinationString.MaximumLength]
0x1400284f4  mov     ecx, 1
0x1400284f9  mov     cs:String1.MaximumLength, ax
0x140028500  mov     eax, dword ptr [rbp+57h+DestinationString+4]
0x140028503  mov     dword ptr cs:String1+4, eax
0x140028509  mov     rax, [rbp+57h+DestinationString.Buffer]
0x14002850d  mov     cs:String1.Buffer, rax
0x140028514  movzx   eax, [rbp+57h+Source.Length]
0x140028518  add     ax, [rbp+57h+SourceString.Length]
0x14002851c  movzx   edx, ax
0x14002851f  mov     cs:Destination.MaximumLength, dx
0x140028526  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002852a  call    LuafvAllocatePool
0x14002852f  mov     cs:Destination.Buffer, rax
0x140028536  test    rax, rax
0x140028539  jnz     short loc_14002854E
0x14002853b  mov     rcx, [rbp+57h+Source.Buffer]
0x14002853f  mov     ebx, 0C000009Ah
0x140028544  call    LuafvFreePool
0x140028549  jmp     loc_1400286BA
0x14002854e  lea     rdx, [rbp+57h+SourceString]; SourceString
0x140028552  lea     rcx, Destination; DestinationString
0x140028559  call    cs:__imp_RtlCopyUnicodeString
0x140028560  nop     dword ptr [rax+rax+00h]
0x140028565  lea     rdx, [rbp+57h+Source]; Source
0x140028569  lea     rcx, Destination; Destination
0x140028570  call    cs:__imp_RtlAppendUnicodeStringToString
0x140028577  nop     dword ptr [rax+rax+00h]
0x14002857c  mov     rcx, [rbp+57h+Source.Buffer]
0x140028580  call    LuafvFreePool
0x140028585  xor     edi, edi
0x140028587  lea     rbx, cs:140000000h
0x14002858e  cmp     edi, 2
0x140028591  jnb     loc_1400286B1
0x140028597  mov     esi, edi
0x140028599  lea     r8, [rbp+57h+Handle]
0x14002859d  shl     rsi, 4
0x1400285a1  xor     ecx, ecx
0x1400285a3  lea     rdx, [rsi+2B170h]
0x1400285aa  add     rdx, rbx
0x1400285ad  call    LuafvOpenKey
0x1400285b2  mov     ebx, eax
0x1400285b4  test    eax, eax
0x1400285b6  js      loc_1400286BA
0x1400285bc  lea     rbx, cs:140000000h
0x1400285c3  xor     r15d, r15d
0x1400285c6  mov     r14, [rsi+rbx+2B138h]
0x1400285ce  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1400285d2  cmp     r15d, [rsi+rbx+2B140h]
0x1400285da  jnb     loc_140028696
0x1400285e0  lea     r9, [rbp+57h+LinkTarget]
0x1400285e4  xor     r8d, r8d
0x1400285e7  mov     rdx, r14; ValueName
0x1400285ea  call    QueryStringValue
0x1400285ef  mov     ebx, eax
0x1400285f1  test    eax, eax
0x1400285f3  js      loc_1400286BA
0x1400285f9  movzx   eax, [rbp+57h+LinkTarget.Length]
0x1400285fd  mov     r8b, 1
0x140028600  add     ax, cs:GlobalRoot.Length
0x140028607  mov     ecx, 1
0x14002860c  movzx   edx, ax
0x14002860f  mov     [rbp+57h+Source.MaximumLength], dx
0x140028613  call    LuafvAllocatePool
0x140028618  mov     [rbp+57h+Source.Buffer], rax
0x14002861c  test    rax, rax
0x14002861f  jz      loc_140028493
0x140028625  lea     rdx, GlobalRoot; SourceString
0x14002862c  lea     rcx, [rbp+57h+Source]; DestinationString
0x140028630  call    cs:__imp_RtlCopyUnicodeString
0x140028637  nop     dword ptr [rax+rax+00h]
0x14002863c  lea     rdx, [rbp+57h+LinkTarget]; Source
0x140028640  lea     rcx, [rbp+57h+Source]; Destination
0x140028644  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002864b  nop     dword ptr [rax+rax+00h]
0x140028650  xor     r8d, r8d
0x140028653  lea     rdx, [rbp+57h+SourceString]
0x140028657  lea     rcx, [rbp+57h+Source]
0x14002865b  call    TranslatePath
0x140028660  mov     rcx, [rbp+57h+Source.Buffer]
0x140028664  mov     ebx, eax
0x140028666  call    LuafvFreePool
0x14002866b  test    ebx, ebx
0x14002866d  js      short loc_1400286BA
0x14002866f  movsxd  rax, dword ptr [r14+10h]
0x140028673  lea     rbx, cs:140000000h
0x14002867a  movups  xmm0, xmmword ptr [rbp+57h+SourceString.Length]
0x14002867e  add     rax, rax
0x140028681  inc     r15d
0x140028684  add     r14, 18h
0x140028688  movdqu  rva StaticEntryRoots[rbx+rax*8], xmm0
0x140028691  jmp     loc_1400285CE
0x140028696  call    cs:__imp_ZwClose
0x14002869d  nop     dword ptr [rax+rax+00h]
0x1400286a2  inc     edi
0x1400286a4  mov     [rbp+57h+Handle], 0
0x1400286ac  jmp     loc_14002858E
0x1400286b1  xor     ebx, ebx
0x1400286b3  jmp     short loc_1400286BA
0x1400286b5  mov     ebx, 0C0000095h
0x1400286ba  mov     rcx, [rbp+57h+LinkHandle]; Handle
0x1400286be  test    rcx, rcx
0x1400286c1  jz      short loc_1400286CF
0x1400286c3  call    cs:__imp_ZwClose
0x1400286ca  nop     dword ptr [rax+rax+00h]
0x1400286cf  mov     rcx, [rbp+57h+Handle]; Handle
0x1400286d3  test    rcx, rcx
0x1400286d6  jz      short loc_1400286E4
0x1400286d8  call    cs:__imp_ZwClose
0x1400286df  nop     dword ptr [rax+rax+00h]
0x1400286e4  mov     rcx, [rbp+57h+DestinationString.Buffer]
0x1400286e8  test    rcx, rcx
0x1400286eb  jz      short loc_1400286F2
0x1400286ed  call    LuafvFreePool
0x1400286f2  mov     eax, ebx
0x1400286f4  mov     rbx, [rsp+0B0h+arg_10]
0x1400286fc  add     rsp, 90h
0x140028703  pop     r15
0x140028705  pop     r14
0x140028707  pop     rdi
0x140028708  pop     rsi
0x140028709  pop     rbp
0x14002870a  retn
```
