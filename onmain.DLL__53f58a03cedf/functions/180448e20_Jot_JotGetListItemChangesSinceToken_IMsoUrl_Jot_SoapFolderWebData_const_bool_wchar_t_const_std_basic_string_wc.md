# Jot::JotGetListItemChangesSinceToken(IMsoUrl *,Jot::SoapFolderWebData const &,bool,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,uint &,uint &,Jot::CMap<unsigned __int64,Jot::FileDescriptionInformation,Jot::HashHelper<unsigned __int64,0>,std::equal_to<unsigned __int64>> &,MsoCF::CArrayInHeapBuffer<Jot::FileChangeInformation> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180448e20`
- end: `0x18044a53a`
- name: `?JotGetListItemChangesSinceToken@Jot@@YA?AW4ListItemError@1@PEAUIMsoUrl@@AEBUSoapFolderWebData@1@_NPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAI5AEAV?$CMap@_KUFileDescriptionInformation@Jot@@U?$HashHelper@_K$0A@@2@U?$equal_to@_K@std@@@1@AEAV?$CArrayInHeapBuffer@UFileChangeInformation@Jot@@@MsoCF@@4@Z`
- size: `5914`
- prototype: `__int64 __fastcall(int, int, int, int, void *, __int64, __int64, __int64, __int64, void *)`
- caller_count: `2`
- callee_count: `40`
- tags: `broker_com_uri`

## callers

- `0x1804489e8`
- `0x180770e38`

## callees

- `0x18002e520`
- `0x18002efb0`
- `0x18002fa9c`
- `0x1800581b0`
- `0x18005cab0`
- `0x18007329b`
- `0x1800734c8`
- `0x180081214`
- `0x180094038`
- `0x180094440`
- `0x180164b00`
- `0x18022aa14`
- `0x1802454bc`
- `0x18028e7e4`
- `0x1802a63f0`
- `0x1802b0cb8`
- `0x1802e2190`
- `0x1802e4c00`
- `0x1802e50d0`
- `0x1802e5170`
- `0x1802e5190`
- `0x18040e428`
- `0x180448428`
- `0x18044847c`
- `0x180448668`
- `0x180448938`
- `0x180448e20`
- `0x18044a59c`
- `0x18044a970`
- `0x18044a9cc`
- `0x18044aa44`
- `0x18044aadc`
- `0x180561ec0`
- `0x180591c98`
- `0x180597460`
- `0x1805c05d8`
- `0x1805c22d4`
- `0x180a641f8`
- `0x180a738bc`
- `0x180a73920`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x180449882`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180449882`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18044987b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18044987b`
- `Mso30Win32Client!__imp_?GetListItemChangesSinceToken@Csi@@YAJPEB_W00_N00AEAV?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CBuffer@_W@2@@MsoCF@@AEAI3PEAPEAUISharePointListItems@1@22@Z` at `0x180449014`
- `Mso30Win32Client!__imp_?GetListItemChangesSinceToken@Csi@@YAJPEB_W00_N00AEAV?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CBuffer@_W@2@@MsoCF@@AEAI3PEAPEAUISharePointListItems@1@22@Z` at `0x180449014`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180448ead`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180448ead`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180449052`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18044906e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180449827`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180449a09`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18044a2a5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180449052`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18044906e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180449827`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180449a09`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18044a2a5`
- `Mso20Win32Client!__imp_?MsoFGuidFromWz@@YAHPEB_WPEAU_GUID@@@Z` at `0x18044971a`
- `Mso20Win32Client!__imp_?MsoFGuidFromWz@@YAHPEB_WPEAU_GUID@@@Z` at `0x18044971a`
- `Mso20Win32Client!__imp_MsoParseUInt64Wz` at `0x1804497aa`
- `Mso20Win32Client!__imp_MsoParseUInt64Wz` at `0x1804497aa`

## string_xrefs

- `0x18044914a`: `OriginalToken`
- `0x1804491b4`: `FolderPath`
- `0x180449232`: `GetListItemChangesSinceToken`
- `0x18044a43d`: `GetListItemChangesSinceTokenFailed`
- `0x180449a94`: `IntialTokenEmpty`

## pseudocode

```c

```
