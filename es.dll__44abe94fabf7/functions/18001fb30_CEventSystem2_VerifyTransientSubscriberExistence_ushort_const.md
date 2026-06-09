# CEventSystem2::VerifyTransientSubscriberExistence(ushort const *)

- ea: `0x18001fb30`
- end: `0x18001fca6`
- name: `?VerifyTransientSubscriberExistence@CEventSystem2@@UEAAJPEBG@Z`
- size: `374`
- prototype: `int(CEventSystem2 *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003d54`
- `0x180010410`
- `0x18001fb30`
- `0x18001fcac`
- `0x1800434de`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fbff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fbff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fbe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fbe5`

## string_xrefs

- `0x18001fc78`: `com\complus\src\events\tier2\eventsystem2.cpp`

## pseudocode

```c
__int64 __fastcall CEventSystem2::VerifyTransientSubscriberExistence(struct _RTL_CRITICAL_SECTION *this, OLECHAR *a2)
{
  OLECHAR *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rsi
  __int64 i; // rcx
  const OLECHAR *v9; // rcx
  OLECHAR *v10; // rcx
  __int64 v11; // rcx

  if ( LODWORD(this[10].DebugInfo) )
    return 2147549448LL;
  if ( !a2 )
    InternalError(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x70Cu, 0x80001203, 0x11u);
  if ( !wcscmp_0(a2, L"ALL") )
  {
    if ( this->SpinCount )
    {
      CSemExclusiveES::Lock((CSemExclusiveES *)&this[3]);
      if ( this[1].RecursionCount )
      {
        v7 = -1;
        do
        {
          v5 = (OLECHAR *)&dword_180053104;
          v6 = v7;
          if ( v7 == -1 && this[1].LockCount )
          {
            v11 = 0;
            do
            {
              v6 = *((_QWORD *)&this[1].DebugInfo->Type + v11);
              if ( v6 )
                break;
              v11 = (unsigned int)(v11 + 1);
            }
            while ( (unsigned int)v11 < this[1].LockCount );
          }
          v7 = *(_QWORD *)v6;
          if ( !*(_QWORD *)v6 )
          {
            for ( i = (unsigned int)(*(_DWORD *)(v6 + 8) + 1);
                  (unsigned int)i < this[1].LockCount;
                  i = (unsigned int)(i + 1) )
            {
              v7 = *((_QWORD *)&this[1].DebugInfo->Type + i);
              if ( v7 )
                break;
            }
          }
          v9 = *(const OLECHAR **)(v6 + 16);
          if ( &dword_180053104 != v9 && v9 - 6 != (const OLECHAR *)&qword_1800530F8 )
          {
            v5 = *(OLECHAR **)(v6 + 16);
            _InterlockedIncrement((volatile signed __int32 *)v9 - 3);
          }
          TransientSubChecker::CheckerThread::ScheduleCheck((HANDLE *)&this[6].DebugInfo, v5);
          v10 = v5 - 6;
          if ( v5 - 6 != (OLECHAR *)&qword_1800530F8
            && _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1 )
          {
            CoTaskMemFree(v10);
          }
        }
        while ( v7 );
      }
      LeaveCriticalSection(this + 3);
    }
  }
  else
  {
    TransientSubChecker::CheckerThread::ScheduleCheck((HANDLE *)&this[6].DebugInfo, a2);
  }
  return 0;
}

```

## disassembly

```asm
0x18001fb30  push    rbx
0x18001fb32  push    rbp
0x18001fb33  push    rsi
0x18001fb34  push    rdi
0x18001fb35  push    r13
0x18001fb37  push    r14
0x18001fb39  sub     rsp, 28h
0x18001fb3d  cmp     dword ptr [rcx+190h], 0
0x18001fb44  mov     rbx, rdx
0x18001fb47  mov     rdi, rcx
0x18001fb4a  jz      loc_18001FC14
0x18001fb50  mov     eax, 80010108h
0x18001fb55  jmp     loc_18001FC07
0x18001fb5a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001fb5e  lea     r13, dword_180053104
0x18001fb65  lea     r9, qword_1800530F8
0x18001fb6c  mov     rbx, r13
0x18001fb6f  mov     rdx, rsi
0x18001fb72  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001fb76  jz      loc_18001FC49
0x18001fb7c  mov     rsi, [rdx]
0x18001fb7f  test    rsi, rsi
0x18001fb82  jnz     short loc_18001FBA2
0x18001fb84  mov     ecx, [rdx+8]
0x18001fb87  inc     ecx
0x18001fb89  cmp     ecx, [rdi+30h]
0x18001fb8c  jnb     short loc_18001FBA2
0x18001fb8e  mov     r8, [rdi+28h]
0x18001fb92  mov     rsi, [r8+rcx*8]
0x18001fb96  test    rsi, rsi
0x18001fb99  jnz     short loc_18001FBA2
0x18001fb9b  inc     ecx
0x18001fb9d  cmp     ecx, [rdi+30h]
0x18001fba0  jb      short loc_18001FB92
0x18001fba2  mov     rcx, [rdx+10h]
0x18001fba6  cmp     r13, rcx
0x18001fba9  jz      short loc_18001FBBA
0x18001fbab  lea     rax, [rcx-0Ch]
0x18001fbaf  cmp     rax, r9
0x18001fbb2  jz      short loc_18001FBBA
0x18001fbb4  mov     rbx, rcx
0x18001fbb7  lock inc dword ptr [rax]
0x18001fbba  mov     rdx, rbx; psz
0x18001fbbd  lea     rcx, [rdi+0F0h]; this
0x18001fbc4  call    ?ScheduleCheck@CheckerThread@TransientSubChecker@@QEAAXPEBG@Z; TransientSubChecker::CheckerThread::ScheduleCheck(ushort const *)
0x18001fbc9  lea     rcx, [rbx-0Ch]; pv
0x18001fbcd  lea     r9, qword_1800530F8
0x18001fbd4  cmp     rcx, r9
0x18001fbd7  jz      short loc_18001FBF2
0x18001fbd9  or      eax, 0FFFFFFFFh
0x18001fbdc  lock xadd [rcx], eax
0x18001fbe0  cmp     eax, 1
0x18001fbe3  jnz     short loc_18001FBF2
0x18001fbe5  call    cs:__imp_CoTaskMemFree
0x18001fbeb  lea     r9, qword_1800530F8
0x18001fbf2  test    rsi, rsi
0x18001fbf5  jnz     loc_18001FB6C
0x18001fbfb  lea     rcx, [rdi+78h]; lpCriticalSection
0x18001fbff  call    cs:__imp_LeaveCriticalSection
0x18001fc05  xor     eax, eax
0x18001fc07  add     rsp, 28h
0x18001fc0b  pop     r14
0x18001fc0d  pop     r13
0x18001fc0f  pop     rdi
0x18001fc10  pop     rsi
0x18001fc11  pop     rbp
0x18001fc12  pop     rbx
0x18001fc13  retn
0x18001fc14  test    rbx, rbx
0x18001fc17  jz      short loc_18001FC73
0x18001fc19  lea     rdx, aAll; "ALL"
0x18001fc20  mov     rcx, rbx; String1
0x18001fc23  call    wcscmp_0
0x18001fc28  test    eax, eax
0x18001fc2a  jnz     short loc_18001FC92
0x18001fc2c  mov     rax, [rdi+20h]
0x18001fc30  test    rax, rax
0x18001fc33  jz      short loc_18001FC05
0x18001fc35  lea     rcx, [rdi+78h]; this
0x18001fc39  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x18001fc3e  cmp     dword ptr [rdi+34h], 0
0x18001fc42  jz      short loc_18001FBFB
0x18001fc44  jmp     loc_18001FB5A
0x18001fc49  cmp     dword ptr [rdi+30h], 0
0x18001fc4d  jbe     loc_18001FB7C
0x18001fc53  mov     r8, [rdi+28h]
0x18001fc57  xor     ecx, ecx
0x18001fc59  mov     rdx, [r8+rcx*8]
0x18001fc5d  test    rdx, rdx
0x18001fc60  jnz     loc_18001FB7C
0x18001fc66  inc     ecx
0x18001fc68  cmp     ecx, [rdi+30h]
0x18001fc6b  jnb     loc_18001FB7C
0x18001fc71  jmp     short loc_18001FC59
0x18001fc73  mov     edx, 70Ch; unsigned int
0x18001fc78  lea     rcx, aComComplusSrcE_18; "com\\complus\\src\\events\\tier2\\event"...
0x18001fc7f  mov     r9d, 11h; unsigned __int16
0x18001fc85  mov     r8d, 80001203h; unsigned int
0x18001fc8b  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001fc90  jmp     short loc_18001FC19
0x18001fc92  lea     rcx, [rdi+0F0h]; this
0x18001fc99  mov     rdx, rbx; psz
0x18001fc9c  call    ?ScheduleCheck@CheckerThread@TransientSubChecker@@QEAAXPEBG@Z; TransientSubChecker::CheckerThread::ScheduleCheck(ushort const *)
0x18001fca1  jmp     loc_18001FC05
```
